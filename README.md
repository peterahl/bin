# Shell scripts

The scripts in this folder can be used to run simulations by adding them to the path. This can be done in many ways but in newer versions of ubunt, this is best done by adding them to the .profile in the home directory.

Add the line:
`export PATH="$PATH:/path/to/dir/"`
to your ~/.zshrc (.bash_rc) file


Se the official documentation for more info. [EnviromentVariables](https://help.ubuntu.com/community/EnvironmentVariables)

you might have to make the files executable by running the command: `chmod +x filename`

## DocstringParser
------------------
This script finds the docstrings of the files in the current working directory and parses them into a .md file. These are:
* FIGURES.md for all .py files, where all text within the comments `""" text """` are considered to be docstrings
* SCRIPTS.md for all .hoc files, where all text within the comments `/*#-*-# text #-*-#*/` are considered to be docstrings.
* MODFILES.md for all files, where all text within the comments `/*#-*-# text #-*-#*/` are considered to be docstrings.

## runspecial
-------------
This script fill find the compiled .special file within the mod directory and run the hoc file using that special. runspecial needs one argument and takes an optional second argument as such:  
`runspecial hocfile.hoc figure.py` where the second argument for figure is optional.

### Important
-------------
If you want to use the build scripts for latex, you have to change a flag to allow bibtex to write to hiden directories

you can do this by:
change openout_any = p to `openout_any = a` in
`/usr/share/texlive/texmf-dist/web2c/texmf.cnf`
if you use a hiden sub directory

Also. It's important that the modfiles are stored in a sub directory to hocfiles we want to run.
