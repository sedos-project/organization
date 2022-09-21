# Organization and Documentation of the SEDOS project

This repository holds the documentation files of the SEDOS project and is also used for managing organizational issues. 

## How to use sedos-project/.github and sedos-project/organisation?

1. Clone repositories

2. create new environment

   $ conda create -n d_py310_sedos python=3.10

3. install mkdocs

   $ pip install mkdocs

4. create or modify .md files in `organisation/docs`

5. navigate to the path, in which you stored ../sedos-project/organisation

   $ cd [USERPATH/sedos-project/organisation]

6. render documentation locally by running mkdocs 

   $ mkdocs serve

   and copy **url** from the INFO message into your browser, e.g.
   
   INFO     -  [11:25:42] Serving on **http://127.0.0.1:8000/**

   Once started, mkdocs shows your local edits live in the browser without further do.

8. Add all your local changes to commit

   $ git add .

9. Commit your local changes

   $ git commit -m 'Extend documentation'

10. Push commit

    $ git push


## How to upload new .md files? 

[**TODO:write detailed documentation**]

