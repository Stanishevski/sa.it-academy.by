#### 04.GitOps
```bash
name: changes
on: [push]
jobs:
  build-matrix:
    runs-on: ubuntu-latest
    name: Building matrix  
    outputs:
      matrix: ${{ steps.set-matrix.outputs.array }}
    steps:
      - name: Clone repo
        uses: actions/checkout@v3
        with:
          fetch-depth: 0
      
      - name: Get changed files
        id  : changed-files
        uses: tj-actions/changed-files@v34
        with:
          json: "true"
      
      - name: Make matrix
        id  : make-matrix
        run : cat 04.GIT_actions/test.json
      
      - name: List files in folder
        run : ls -ll
        
      - name: List matrix
        run: echo ${{ steps.make-matrix }} 
      
      
      - name: set matrix
        id  : set-matrix
        run : echo "array={\"container\":${{ steps.changed-files.outputs.all_changed_files }}}" >> "$GITHUB_OUTPUT"
  

  build:
    needs  : build-matrix
    runs-on: ubuntu-latest 
    name   : Test changed-files

    strategy:
        matrix: ${{ fromJSON(needs.build-matrix.outputs.matrix) }}
    steps:
      - name: Clone repo
        uses: actions/checkout@v3
        with:
          fetch-depth: 0
      
      - name: Files check
        id  : set-env
        run: |
          COUNTER=$(cat ${{ matrix.container }} | tr -dc \\t | wc -c)      
          FILENAME=$(echo  ${{ matrix.container }} | sed 's|.*/||')
          echo "In the file $FILENAME is $COUNTER tabs" >> $FILENAME.log
          echo "filename=$FILENAME"
          echo "filename=$FILENAME" >> $GITHUB_ENV
      - name: Show filensme
        run: echo ${{ env.filename }}
      - name: Upload logs
        uses: actions/upload-artifact@v2
        with:
          path: ${{ env.filename }}.log

```
