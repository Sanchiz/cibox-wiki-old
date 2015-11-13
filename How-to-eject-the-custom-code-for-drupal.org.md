1 - Pretty standard development for the module in sites/all/modules/custom/MODULENAME
2 - Run a command 
git filter-branch --subdirectory-filter hpmatter/sites/all/modules/custom/MODULENAME HEAD
This command will remove all commits from history instead of those, dependent from this MODULENAME
Also it will reorganize folder structure to only MODULENAME folder content as git repo root.
3 git filter-branch --tree-filter 'rm -f passwords.txt' HEAD
This command will remove all sensitive data from repo and history about it. You can use Your own script for preg replacing data in files too.
4 run shell script

git filter-branch --commit-filter '
if [ "$GIT_AUTHOR_EMAIL" = "developer@corporate.example.com" ];
then
GIT_AUTHOR_NAME="Dream Developer";
GIT_AUTHOR_EMAIL="opensource.developer@drupal.example.com";
git commit-tree "$@";
else
git commit-tree "$@";
fi' HEAD

This script will change corporate user email to that is used at drupal.org for tracking statistics.

5 - git push DRUPALORG_MAINTAINERNAME@git.drupal.org:project/PROJECTNAME.git
for pushing data to drupal.org project.