# Student Performance - Machine Learning End to End Project

- To create vertual environment with conda
--- 
    conda create -p envname python==3.8 -y
---

- Activate the vertual environment with conda
---
    conda activate envname/
---

- Create git repo , and after that clone this repository to vscode
---
    git init
---

- Create README.md file in vs code and add this file to the repository
---
    git add README.md
---

- To commit any file to repository
---
    git commit -m "message"
---

- To see the git satus
---
    git status
---

- To check the branch- main
---
    git branch -M main
---

- To sink with repository add th file to main branch
---
    git remote add origin https://github.com/dinesh4444/StudPerformance.git
---

- If you are doing for first time that time you have to set git global config
---
    git config --global user.name "your user name"
    git config --global user.email "your email address"
---

- To push data from vscode to git repository
---
    git push -u origin main
---

- To pull data from git repository
---
    git pull 
---
--------------------------------------------------------------------------------------

Create setup.py file which store the meta data of your project
   
    from setuptools import find_packages, setup

    setup(
        name="Student Performance MLproject",
        version='0.0.1',
        author='author name',
        author_email='your email address',
        packages=find_packages(),
        install_requires=get_requirements('requirements.txt'),
        
    )

---------------------------------------------------------------------------------------




