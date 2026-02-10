<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up a Web App in the Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-vscode)

**Author:** Trupti Vibhute  
**Email:** trupti.v19625@gmail.com

---

## Set Up a Web App Using AWS and VS Code

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-vscode_7a1de541)

---

## Introducing Today's Project!

In this project, Im gonna be learning the basics of a web app  ... I'm doing this project to learn more about the devops side of things and also because its related to cloud.

This project is part one of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project soon....

I did this project to understand more about AWS services and how its linke to devops.

### Key tools and concepts

Services I used were AWS EC2, remote SSH, SFTP, terminal, VSCode... Key concepts I learnt include accessing an EC2 instance remotely using keypairs and through the terminal.

### Project reflection

This project took me approximately 3 hrs... The most challenging part was connecting the vscode to my instance and viewing all the files and folders... It was most rewarding tosee all the files showing up in my vscpde explorer.

One thing I didn't expect in this project was -- remote ssh throwing this one error at me which i couldnt fix for 2 hours.

---

## Launching an EC2 instance

### What I did in this step

In this step, I will be launching an EC2 instance and set aup a key pair for secure ssh access to the instance.
Also need to configure some network settings for the instance.

I started this project by launching an EC2 instance because we are gonna launch a web app inside this instance using Apache Maven and Amazon Corretto 8

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-vscode_7852fbf3)

### I also enabled SSH

SSH i.e. Secure Shell is a protocol used to make sure only authorized users can access a remote server. When you connect to your EC2 instance later in this project, SSH verifies you have the correct private key that matches the public key on the server.

I enabled SSH traffic because i'm gonna be connecting to this instance using ssh later.

### Key pairs

A key pair is like the keys to your computers. They ar used to securely access the EC2 instance.
AWS keeps the public key and we have the private key.

### Downloaded key pair file

Once I set up my key pair, AWS automatically downloaded the private key which was in the .pem format

---

## Set up VS Code

### What I did in this step

In this step, I will open vs code because we are gonna change the permissions of the .pem file from the vscode terminal.

### What is VS Code?

Visual Studio Code (VS Code) is one of the most popular tools for creating and managing coding projects. You'll often hear people call VS Code an IDE (Integrated Development Environment), which means software that help you write and edit code. It's similar to how Microsoft Word or Google Docs help you write documents!

I installed VS Code because this is where  im gonna be changing thr permissions of my .pem file.

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-vscode_53d05e68)

---

## My first terminal commands

A terminal is where you send instructions to your computer using text instead of clicks. 

The commands I ran for this project were:
cd (Change Directory): This command is used to move between folders in your file system.

~ represents your home directory i.e. the starting point of a computer's file system. For most users, this is where you begin when you open the terminal.

/Desktop/DevOps tells your terminal how to get from your home directory to the DevOps folder. The forward slashes (/) are used to separate each directory in the path.

### Updating file permissions

I also updated my private key's permissions by entering the following commanf:

chmod 400 nextwork-keypair.pem

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-vscode_9328ada1)

---

## SSH connection to EC2 instance

### What I did in this step

In this step, I will be connecting to my EC2 instance through vscode to launch the web app there.

### Connecting to EC2

To connect to my EC2 instance, I ran the command:

ssh -i ~/Desktop/DevOps/nextwork-keypair.pem ec2-user@~/Desktop/DevOps/nextwork-keypair.pem

### This command required an IPv4 address

A Public IPv4 DNS (which stands for Domain Name System) is the public address for your EC2 server that the internet uses to find and connect to it. The local computer you're using to do this project will find and connect to your EC2 instance through this IPv4 DNS.


![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-vscode_e3069dca)

---

## Maven & Java

### What I did in this step

In this step, I will install Apache Maven and Amazn corretto 8 ... because which will help us t build java app

### Why I'm using Maven

Apache Maven is a powerful tool that automates the building of software.

Maven is required in this project to automate the process of building the web app.
this process includes code compilation, linking the code with additional dependencies, packaging and testing,
Apache MAven automates these processes for us.

### Why I'm using Java

Java is a popular programming language used to build different types of applications, from mobile apps to large enterprise systems.

Amazon Corretto 8 is a version of Java that we're using for this project. It's free, reliable and provided by Amazon.

Java is required in this project because we are building a web app using that programming language.

---

## Create the Application

### What I did in this step

In this step, I will run some maven commands in my terminal to generate a java web app.

### Creating the Java web app

I generated a Java web app using the commands below:

mvn archetype:generate \
   -DgroupId=com.nextwork.app \
   -DartifactId=nextwork-web-project \
   -DarchetypeArtifactId=maven-archetype-webapp \
   -DinteractiveMode=false

When you run mvn commands, you're asking Maven to perform tasks (like creating a new project or building an existing one).

The mvn archetype:generate command specifically tells Maven to create a new project from a template (which Maven calls an archetype). This command sets up a basic structure for your project, so you don't have to start from scratch.

### Installing Remote - SSH

The Remote - SSH extension in VS Code lets you connect directly via SSH to another computer securely over the internet. This lets you use VS Code to work on files or run programs on that server as if you were doing it on your own computer, which will come in handy when we edit the web app in your EC2 instance!

### SSH configuration details

Configuration details required to set up a remote connection include the public ip address of my EC2 instance, host name, identity file and user.

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-vscode_2939cf01)

---

## Create the Application

### Exploring the project structure

Using VS Code's file explorer, I could see all the files which were present on my ec2 instance.

TWIST:
i intially tried connecting using the remote ssh extension but it was failing due to some reason. I took time, didnt rush it and tried to fix the error by trying so many different methods but i was getting the same error. 
at last i tried using a different extension and voilaa!! it worked !!

The src (source) folder holds all the source code files that define how your web app looks and works.



src is further divided into webapp, which are the web app's files e.g. HTML, CSS, JavaScript, and JSP files, and resources, which are the configuration files a web app might need e.g. connection settings to a database.



pom.xml is a Maven Project Object Model file. It stores information and configuration details that Maven will use to build the project. We'll use pom.xml later in this project series


![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-vscode_45f91fd7)

---

## Using Remote - SSH

### What I did in this step

In this step, I will:

Install an extension in VS Code.
Use the extension to set up a connection between VS Code and my EC2 instance
Explore and edit my java web app's files using VS Code.

### Updating the web app

index.jsp is a file used in Java web apps. It's similar to an HTML file because it contains markup to display web pages.

However, index.jsp can also include Java code, which lets it generate dynamic content.

I edited index.jsp by entering my name there.

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-vscode_7a1de541)

---

## Using nano

### Additional improvements

In this secret mission, I will Edit index.jsp using the terminal instead of an IDE.

### Terminal vs IDE

An alternative to using IDEs is to directly access your ec2 content and files through your terminal. To edit index.jsp, I ran the command cd, pwd and s until i found the right folder and then ran nano index.jsp.

Compared to using an IDE, editing index.jsp in the terminal felt very time  consuming.

### Verifying my work

To verify my editing work in the terminal, I checked if it was refected in my ther vscode window where ive used sftp to connect to my instance. It was possible to view the changes after i cicked on the index.jsp fille and clicked download. Doing this would pull any new changes made to the file.

![Image](http://learn.nextwork.org/appreciative_brown_zany_lemon/uploads/aws-devops-vscode_a3324ad41)

---

---
