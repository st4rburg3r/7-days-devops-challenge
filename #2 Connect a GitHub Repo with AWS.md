<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Connect a GitHub Repo with AWS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-github)

**Author:** Trupti Vibhute  
**Email:** trupti.v19625@gmail.com

---

## Connect a GitHub Repo with AWS

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-github_dd9d254e)

---

## Introducing Today's Project!

In this project, I will demonstrate how to:
🐱 Set up Git and GitHub.
🤝 Connect your web app project to a GitHub repo.
🪄 Make changes to your web app code - and watch your GitHub repo update too.
💎 Set up a README file for your repo.... 

I'm doing this project to learn about devops and ci/cd pipelines.


### Key tools and concepts

Services I used were AWS EC2, VSCode, Github

### Project reflection

This project took me approximately 1 hr

I did this project because i wanted to learn more about github, ci/cd pipelines and workflows

This project is part two of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project right away.

---

## Git and GitHub

Git is like a time machine and filing system for your code. It tracks every change you make, which lets you go back to an earlier version of your work if something breaks.

You can also see who made specific changes and when they were made, which makes teamwork/collaboration a lot easier.

If Git is the tool for tracking changes, think of GitHub as a storage space for different version of your project that Git tracks. Since GitHub is a cloud service, it also lets you access your work from anywhere and collaborate with other developers over the internet. 

I'm using GitHub in this project because GitHub helps to use Git and see your file changes in a more user-friendly way. It's just like how using an IDE (VSCode) makes editing code easy.

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-github_efaadbf7)

---

## My local repository

To store your code using Git, you create repositories (aka 'repos'), which are folders that contain all your project files and their entire version history. Hosting a repo in the cloud, like on GitHub, means you can also collaborate with other engineers and access your work from anywhere.

To start using Git for your project, you need to create a local repository on your computer.

When you run git init inside a directory e.g. nextwork-web-project, it sets up the directory as a local Git repository which means changes are now tracked for version control.

A branch in Git is... After running git init, the response from the terminal was...

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-github_7bf21bae)

---

## To push local changes to GitHub, I ran three commands

### git add

The first command I ran was git add . 
this command  stages all (marked by the '.') files in nextwork-web-project to be saved in the next version of your project.
When you stage changes, you're telling Git to put together all your modified files for a final review before you commit them. This is incredibly handy because you get to see all your edits in one spot, which means its much easier to check if there were are mistakes or unwanted changes before you commit.

### git commit

The second command I ran was git commit -m "Updated index.jsp with new content".
-m flag lets you leave a message describing what the commit is about, making it easier to review what changed in this version.

### git push

The third command I ran was git push -u origin master
... Using '-u' means you're also setting an 'upstream' for your local branch, which means you're telling Git to remember to push to master by default. Next time, you can simply run git push without needing to define origin and master.

---

## Authentication

When I commit changes to GitHub, Git asks for my credentials because  there are too many security risks and passwords can get intercepted over the internet 🤺 You need to use a personal access token instead, which is a more secure method for logging in and interacting with your repos.

### Local Git identity

Git needs author information for commits to track who made what change. If you don't set it manually, Git uses the system's default username, which might not accurately represent your identity in your project's version history.

Run git log to see your history of commits, which also mentions the commit author's name.



![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-github_9a27ee3b)

---

## GitHub tokens

GitHub authentication failed when I entered my password because we need to use a personal access token instead, which is a more secure method for logging in and interacting with your repos.

A token in GitHub is a unique string of characters that looks like a random password. For example, a GitHub token might look like ghp_xHJNmL16GHSZSV88hjP5bQ24PRTg2s3Xk9ll. As you can imagine, tokens are great for security because they're unique and would be very hard to guess.
. I'm using one in this project because its a new common security practice to log in usng tokens

I could set up a GitHub token by generating a new classic token from developer settings

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-github_fa11169d)

---

## Making changes again

I wanted to see Git working in action, so I. updated my index.jsp file from vscode and pushed those changes to github.

I finally saw the changes in my GitHub repo after i committed the changes and pushed them to github.


![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-github_6becb2bc)

---

## Setting up a READMe file

As a finishing touch to my GitHub repository, I added a README file, which is document that introduces and explains your project, like what the project does, how to set it up, and how to use it. I added a README file by typing touch README.md in the aws terminal.


My README is written in Markdown
It is a text language that lets you format text that you'll display on a webpage. With Markdown, you can make words bold, create headers, add links, and use bullet points - all with simple symbols added to your text.

It’s useful for creating documents like README files that need to look clean and easy to read without complex software, making it a favorite for writing on platforms like GitHub

My README file has 5 sections that outline introduction, technology, setup, contact, contact, conclusion

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-github_c94976902)

---

---
