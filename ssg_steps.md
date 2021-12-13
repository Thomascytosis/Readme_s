The following are instructions for ***Windows Users*** but with some slight command variation may work for Linux and Mac.

# Requirements

- Python [Link](https://www.python.org/downloads/) 
- GH [Link](https://cli.github.com/manual/index) 
- Git [Link](https://git-scm.com/downloads) 
- Pipenv [Link](https://pipenv.pypa.io/en/latest/install/) `pip install pipenv`

## Project Steps 

1. open console
2. create directory for project 

` mkdir 'folder_name'` 

3. open directory in console 

` cd 'folder_name'` 

4. start tracking this directory 

` git init` 

5. start a shell to run and install dependencies 

` pipenv shell` 

6. install pelican 

` pipenv install pelican` 

7. install markdown 

` pipenv install markdown` 

8. install invoke 

` pipenv install invoke` 

9. install livereload 

` pipenv install livereload` 

10. run Pelican Quickstart 

` pelican-quickstart`  
>What will be the title of this web site?`website_name`  
>Who will be the author of this web site?`author_name`  
>What will be the default language of this web site? [English]`en`  
>Do you want to specify a URL prefix? e.g., https://example.com (Y/n)`n`  
>Do you want to enable article pagination? (Y/n)`n`  
>What is your time zone? [Europe/Rome]`America/Denver`  
>Do you want to generate a tasks.py/Makefile to automate generation and publishing? (Y/n)`y`  
>Do you want to upload your website using FTP? (y/N)`n`  
>Do you want to upload your website using SSH? (y/N) `n`  
>Do you want to upload your website using Dropbox? (y/N)`n`  
>Do you want to upload your website using S3? (y/N)`n`  
>Do you want to upload your website using Rackspace Cloud Files? (y/N)`n`  
>Do you want to upload your website using GitHub Pages? (y/N)`n`  

Done. Your new project is available in your current directory 
    
11. add images directory, readme file, and markdown file in content folder 

`cd content`  
`mkdir images`  
`echo > readme.txt`  
`copy con {filename}.md`  
>`title: 'title of website'`  
>`date: YYYY-MM-DD`  
>`category: 'home'`  
>`# 'A header for the website'`  
>`'some text for the website'`  
>`ctl + c` to exit  

`cd ..`  

12. check with Pelican 

`pelican`  
>Done: Processed 1 article, 0 drafts, 0 hidden articles, 0 pages, 0 hidden pages and 0 draft pages in 0.16 seconds.  

12. invoke live reload to view webpage 

`invoke livereload` *(starts an active process, see below, and should open your browser)*  

>[I 211209 12:54:59 server:335] Serving on http://localhost:8000  
>[12:54:59] INFO     Serving on http://localhost:8000 server.py:335  
>[I 211209 12:54:59 handlers:62] Start watching changes  
>INFO     Start watching changes handlers.py:62  
>[I 211209 12:54:59 handlers:64] Start detecting changes  
>INFO     Start detecting changes handlers.py:64  
>[I 211209 12:54:59 handlers:135] Browser Connected: http://localhost:8000/  
>INFO     Browser Connected: http://localhost:8000/ handlers.py:135  
>[W 211209 12:54:59 log:91] 404 GET /favicon.ico (::1) 4.00ms  
>WARNING  404 GET /favicon.ico (::1) 4.00ms log.py:91  
>[I 211209 12:55:00 handlers:82] Ignore: C:\Users\thomc\virtualenvs\oily_fish-4An-YCfm\lib\site- packages\pelican\themes\notmyidea/static\fonts\font.css  
>[12:55:00] INFO     Ignore: C:\Users\thomc\.virtualenvs\oily_fish-4An-YCfm\lib\site-packages\pelican\the handlers.py:82 mes\notmyidea/static\fonts\font.css  
>[I 211209 12:55:01 handlers:92] Reload 1 waiters: None  
>[12:55:01] INFO     Reload 1 waiters: None handlers.py:92  

13. View in web browser then return to console  

`ctr + c` to end active process  
>[I 211209 12:55:27 server:358] Shutting down...  
>[12:55:27] INFO     Shutting down... server.py:358  
    
14. install Pelican noJekyll plugin 

`pip install minchin.pelican.plugins.nojekyll`  

15. switch to windowed GUI directory of your project 
    1. locate and open in code editor: **pelicanconf.py** 
    2. add the following code 

    ```
    PLUGINS = [
        # ...
        'minchin.pelican.plugins.nojekyll',
        # ...
    ]
    ``` 

    3. and change the **SITEURL = ''** to the following  

    `SITEURL = '.'`  

    4. and add ***below*** **PATH = 'content'** the following

    `OUTPUT_PATH = 'docs'`  

    5. save and close file 
    6. return to console

16. run python and live reload 

`pelican`  
`invoke livereload`  

close web browser livereload tab and return to console  

`ctrl + c` to exit active console process  

17. create a github repo for this website 

`gh repo create`  

>? What would you like to do? `[Create a new repository on GitHub from scratch]`  
>? Repository Name:`'Repo_name'`  
>? Description:`'Repo_description'`   
>? Visibility`[Public]`  
>? Would you like to add a .gitignore?`[No]`  
>? Would you like to add a license?`[No]`  
>? This will create "Repo_name" as a public repository on GitHub. Continue?`[Yes]`  
>✓ Created repository ***'Github_Id/Repo_name'*** on GitHub  
>? Clone the new repository locally?`[No]`  

1. add all changes to git 

`git add .`  

ignore warnings about LF and CRLF (it is *something for later*)

>warning: LF will be replaced by CRLF in ...  
>The file will have its original line endings in your working directory  

19. stage all the changes to make ready for push to Repo 

`git commit -m "comments about this push and any changes made"`  

20. connect git to Repo on Github 

`git remote add origin git@github.com:'Github_User_Id/Repo_name.git'`   

21. create branch if first time or if needed 

`git branch -M main`  

22. push to Github 

`git push -u origin main`  

enter passphrase if required 

23. switch to browser and go to your Github account and repo. 
    1. direct url should be similiar to `https://github.com/Github_User_Id/Repo_name` 
    2. go to settings tab 
    3. go to pages settings 
    4. select branch : main 
    5. select folder : docs 
    6. click save  

24. Wait a moment for sync 
25. click on the link to your new webpage on Github! 
