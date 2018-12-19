---
layout: post
title: Computing Platform for Data Science
---

Data science requires a comprehensive, robust computing platform. A basic platform for data science may include Github/Git, Jupyter Notebook, R Studio, Atom, etc.

## Github/Git
Github/Git is the most popular platform for version control and team collaboration.

**When working by yourself**  
Basic operations may include:  
- Create a Github account
- Create a repo
- Clone a Github repo to local using below command
```
git clone [REPO_URL]
```
- Edit the local replica of the repo
- Using below commands to sync local changes to Github repo:
```
$ git add .
$ git commit -m "[COMMIT MESSAGE]"
$ git push
```

**Work on a public repo**  
When you want to work on a public repo that was published and managed by someone else, you may `fork` that repo to your account, and then work on your own copy of the repo.

**When a team works on the same project**
When a team works on the same project, create a repo first, then every team member `fork` this repo to their personal account. Then `clone` this forked copy to local and work on the local cloned copy. When a team member make material change to the local repo, he/she firstly need to git add/commit/push the changes to his/her forked copy. Then on Github, go to the forked copy and submit a *Pull Request*, which will be seen by all team members. One team member need to review the pull request and accept it. Lastly, every team member, except the one who created the Pull Request, needs to sync their forked repo and local repo by running below commands:
```
$ git fetch upstream
$ git merge upstream/master
$ git push
```

## Jupyter Notebook
Jupyter Notebook is a powerful tool for Python and R programming. One of its nice features is that it allows you to break code into *chunks* and you can run each chunk separately to see how it works. Another nice feature is that Jupyter Notebook allows you to combine markdown and code in one document.  


## R Studio
R Studio is another mainstream R programming tool. It provides powerful features, such as R Markdown and debugging. R Markdown files are, in some way, similar to Jupyter notebooks. But RMarkdown offers much more control on markdown formatting and code chunk execution.

- A R Markdown file can contain markdown and code chunks, and can be knitted to different file formats, such as PDF, HTML and MD. It can also be knitted into HTML5 slides!  
- Every R Markdown file includes a YAML header, which defines title, author, and output format of knitting. Most common output formats include:
```
html_document	  # HTML
pdf_document	   # PDF
word_document	  # Microsoft Word
md_document	    # Markdown
github_document	# Github compatible markdown
```
- You can control how code chunk be run and included in output. Two examples of controls options:
```
echo=TRUE       # display code in output document
eval=TRUE       # run code in chunk
include=FALSE   # do not include chunk in document after running
```
- There is a [R Markdown Cheatsheet](http://www.rstudio.com/wp-content/uploads/2016/03/rmarkdown-cheatsheet-2.0.pdf) for quick reference.

## Atom
Atom is a versatile, helpful author tool that can be used to author any text-based document, such as .md, .Rmd, .txt, .R, .py, etc. 
