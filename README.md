# Organization and Documentation of the SEDOS project

This repository holds the documentation files of the SEDOS project and is also used for managing organizational issues. 

## How to use sedos-project/.github and sedos-project/organisation?

1. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this repository


2. Navigate to the path, in which you stored ../sedos-project/organisation


      $ cd [USERPATH/sedos-project/organisation]


3. Create new environment by using pre-defined settings from environment.yml and activate it after successful installation
 

      $ conda env create -f environment.yml

      $ conda activate d_py310_sedos

4. Modify .md files in `organisation/docs` or create new .md files by creating a new file and renaming the file extension `.md`.


5. Render documentation locally by running mkdocs 

   
      $ mkdocs serve

   and copy **url** from the INFO message into your browser, e.g.
   

   > INFO     -  [11:25:42] Serving on http://127.0.0.1:8000/

   Once started, mkdocs shows your local edits live in the browser without further do.


6. Add all your local changes

   
      $ git add .

7. Commit your local changes

   
      $ git commit -m 'Extend documentation'

8. Check if other SEDOS members uploaded changes before pushing yours

   
      $ git pull   

9. Push your commits, to share them with the team

    
      $ git push


## How to upload new .md files? 

[**TODO:write detailed documentation**]
###### @SB isn't this section dealt with 4. above?
