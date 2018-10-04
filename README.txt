git clone git@github.com:/jps3318/project1
cd project1/
git subtree split -P dir1 -b dir1-branch
cd ../
mkdir dir1-project
cd dir1-project/
git init
git pull ../project1/ dir1-branch
git remote add origin git@github.com:jps3318/dir1-project.git
git pull origin master --allow-unrelated-histories
git push --set-upstream origin master

# replace the dir with the new project
cd ../project1
git rm -r dir1
git submodule add git@github.com:jps3318/dir1-project dir1
git commit
