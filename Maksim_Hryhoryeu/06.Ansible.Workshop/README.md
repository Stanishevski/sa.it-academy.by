## Result

```
PLAY [nginx] ******************************************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:03 +0000 (0:00:00.008)       0:00:00.008 *******
ok: [nginx_11]

TASK [Prepare. Install packages] **********************************************************************************************************************************************************
Sunday 25 December 2022  14:19:05 +0000 (0:00:01.879)       0:00:01.888 *******
ok: [nginx_11]

TASK [Install nginx] **********************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:08 +0000 (0:00:02.844)       0:00:04.732 *******
ok: [nginx_11]

TASK [Start nginx] ************************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:10 +0000 (0:00:02.700)       0:00:07.432 *******
ok: [nginx_11]

TASK [Show version] ***********************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:11 +0000 (0:00:00.918)       0:00:08.351 *******
changed: [nginx_11]

TASK [debug] ******************************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:12 +0000 (0:00:00.657)       0:00:09.009 *******
ok: [nginx_11] => {
    "msg": "Nginx version: []"
}

TASK [Create folder for pages] ************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:12 +0000 (0:00:00.022)       0:00:09.032 *******
ok: [nginx_11] => (item=page1.dev)
ok: [nginx_11] => (item=page2.dev)

TASK [Copy page] **************************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:13 +0000 (0:00:01.248)       0:00:10.280 *******
ok: [nginx_11] => (item=page1.dev)
ok: [nginx_11] => (item=page2.dev)

TASK [Copy config file] *******************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:15 +0000 (0:00:01.970)       0:00:12.250 *******
ok: [nginx_11] => (item=page1.dev)
ok: [nginx_11] => (item=page2.dev)

TASK [Create link for pages] **************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:17 +0000 (0:00:01.965)       0:00:14.215 *******
changed: [nginx_11] => (item=page1.dev)
changed: [nginx_11] => (item=page2.dev)

TASK [Add entry in hosts] *****************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:18 +0000 (0:00:01.177)       0:00:15.393 *******
changed: [nginx_11] => (item=page1.dev)
changed: [nginx_11] => (item=page2.dev)

TASK [Restart nginx] **********************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:20 +0000 (0:00:01.199)       0:00:16.593 *******
changed: [nginx_11]

TASK [Check site connection] **************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:20 +0000 (0:00:00.775)       0:00:17.368 *******
ok: [nginx_11] => (item=page1.dev)
ok: [nginx_11] => (item=page2.dev)

TASK [Check site] *************************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:22 +0000 (0:00:01.405)       0:00:18.774 *******
ok: [nginx_11] => {
    "msg": "All items completed"
}

TASK [Print page1] ************************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:22 +0000 (0:00:00.022)       0:00:18.796 *******
changed: [nginx_11]

TASK [debug] ******************************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:22 +0000 (0:00:00.640)       0:00:19.437 *******
ok: [nginx_11] => {
    "msg": [
        "<!DOCTYPE html>",
        "<html lang=\"en\">",
        "<head>",
        "\t<title> page1.dev </title>",
        "</head>",
        "<body>",
        "\t<h1> WELCOME TO page1.dev </h1>",
        "\t<h3> Hostname : sa-11<h3>",
        "</body>",
        "</html>"
    ]
}

TASK [Print page2] ************************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:22 +0000 (0:00:00.022)       0:00:19.460 *******
changed: [nginx_11]

TASK [debug] ******************************************************************************************************************************************************************************
Sunday 25 December 2022  14:19:23 +0000 (0:00:00.584)       0:00:20.044 *******
ok: [nginx_11] => {
    "msg": [
        "<!DOCTYPE html>",
        "<html lang=\"en\">",
        "<head>",
        "\t<title> page2.dev </title>",
        "</head>",
        "<body>",
        "\t<h1> WELCOME TO page2.dev </h1>",
        "\t<h3> Hostname : sa-11<h3>",
        "</body>",
        "</html>"
    ]
}

PLAY RECAP ********************************************************************************************************************************************************************************
nginx_11                   : ok=18   changed=6    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

Sunday 25 December 2022  14:19:23 +0000 (0:00:00.044)       0:00:20.089 *******
===============================================================================
Prepare. Install packages ---------------------------------------------------------------------------------------------------------------------------------------------------------- 2.84s
Install nginx ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- 2.70s
Copy page -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 1.97s
Copy config file ------------------------------------------------------------------------------------------------------------------------------------------------------------------- 1.97s
Gathering Facts -------------------------------------------------------------------------------------------------------------------------------------------------------------------- 1.88s
Check site connection -------------------------------------------------------------------------------------------------------------------------------------------------------------- 1.41s
Create folder for pages ------------------------------------------------------------------------------------------------------------------------------------------------------------ 1.25s
Add entry in hosts ----------------------------------------------------------------------------------------------------------------------------------------------------------------- 1.20s
Create link for pages -------------------------------------------------------------------------------------------------------------------------------------------------------------- 1.18s
Start nginx ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ 0.92s
Restart nginx ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- 0.78s
Show version ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- 0.66s
Print page1 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ 0.64s
Print page2 ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ 0.58s
debug ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ 0.04s
debug ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ 0.02s
debug ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ 0.02s
Check site ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 0.02s
Playbook run took 0 days, 0 hours, 0 minutes, 20 seconds
```
