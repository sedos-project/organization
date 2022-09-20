# Organization and Documentation of the SEDOS project

This repository holds the documentation files of the SEDOS project and is also used for managing organizational issues. 

## How to use sedos-project/.github and sedos-project/organisation?

 1. Clone repositories

 2. setup your local environment and install mkdocs
open your environment manager, e.g. miniconda3:

 2.1 create new environment
$ conda create -n d_py310_sedos python=3.10

 2.2 install mkdocs
$ pip install mkdocs

3. create or modify .md files in `organisation/docs`

4. render documentation locally

4.1. navigate to the path, in which you stored ../sedos-project/organisation

4.2. run mkdocs and copy url into your browser
$ mkdocs serve

5. Publish your changes on github

5.1 Add all your local changes to commit
$ git add .

5. Commit your local changes
$ git commit -m 'Extend documentation'

6. Push commit
$ git push


## How to upload new .md files? 

[TODO:write detailed documentation]

