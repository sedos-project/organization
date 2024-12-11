# Organization and Documentation of the SEDOS project

This repository holds the documentation files of the SEDOS project and is also used for managing organizational issues. 

## Documenation release

The documentation will be released with a push on the `main` branch to this [website](https://sedos-project.github.io/organization/). Wait ~ 2min until you can see changes.

The [documentation](https://sedos-project.github.io/organization/) is automatically deployed by the [workflow](https://github.com/sedos-project/organization/blob/main/.github/workflows/build_and_deploy_documentation.yml) on 
the branch `gh-pages`. In the GitHub-pages settings, this branch has been chosen to be the branch from which the 
documentation is deployed. The workflow is triggered with a push to `main` or can be triggered manually in 
GitHub actions.

## How to set up the documentation on your local machine?

1. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this repository 

      `git clone https://github.com/sedos-project/organization.git`


2. Navigate to the path, in which you stored ../sedos-project/organisation

      `cd [USERPATH/sedos-project/organisation]`


3. Create new environment by using pre-defined settings from environment.yml and activate it after successful installation
 
      `conda env create -f environment.yml`

      `conda activate d_py310_sedos`
      

4. Modify .md files in `organisation/docs` or create new .md files by creating a new file and renaming the file extension `.md`.

5. Render documentation locally by running mkdocs `mkdocs serve` and copy **url** from the INFO message into your browser, e.g.
   

   > INFO     -  [11:25:42] Serving on http://127.0.0.1:8000/

   Once started, mkdocs shows your local edits live in the browser without further do.

6. Depending on the amount of changes you want to add, consider creating your own feature branch.
   However, if you only add an independent docs module, you can push it to develop.
   Make sure to checkout the branch you want to work on.

7. Add all your local changes `git add .`

8. Commit your local changes `git commit -m 'Extend documentation`

9. If you have not created your own branch, check if other SEDOS members uploaded changes before pushing yours `git pull`  

10. Push your commits, to share them with the team `git push`.

11. If you have created your own branch, start a pull request.