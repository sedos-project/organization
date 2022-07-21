Test how to upload new .md files and workflow with .github and organisation repos in sedos-project.

 1. Clone repos

 2. setup your local environment and install mkdocs
open your environment manager, e.g. miniconda3:

 3. create new environment
$ conda create -n d_py310_sedos python=3.10

 4. install mkdocs
$ pip install mkdocs

2. create or modify .md files in `organisation/docs`

3. Add all your local changes: 
$ git add .

4. Commit your local changes
$ git commit -m 'Extend documentation'

5. Push commit
$ git push

7. TODO How to deploy on mkdocs