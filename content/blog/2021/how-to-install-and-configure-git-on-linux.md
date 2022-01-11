--- 
title: "How to Install and Configure Git on Linux" 
date: 2022-01-11T04:36:33Z 
description: "This post helps you in setting up and configuring git on you Linux machine. " 
draft: true 
author: "Chaitanya Chaturvedi" 
tags: "git, install, github, linux" 
images:  
- /images/git-octocat.jpg
categories:  
- git
- github
- install
- linux
Summary : In this post I have you will get know about git and how to set it up on your Linux machine. I have summed up each step from installing to configuring git on your Linux machine. I hope you find this post helpful. Happy reading! 

related:
threshold: 80
includeNewer: false
toLower: false
indices:
- name: keywords
weight: 100
name: date
weight: 10
--- 

Probably you have decided to work on a project, and you want to use a VCS to keep the version history of your code or probably you just want to clone something from GitHub or Gitlab. Whatever your motive maybe, if you want to know how to set up Git on your Linux machine then you are probably at the right place. Let's get started! 

# What is Git, and Why you need it? 

In short and simple words, Git is a VCS (Version Control System) that keeps a track record of your code or different versions of your code. What is a VCS you may ask? Again, the same thing, a system that keeps a track record of your code. There are different VCS in the market and Git is one of them. But to be specific, Git is a DVCS (Distributed Version Control System), since git lets the piece of code being distributed to each of the contributor's systems. 

In git a user basically commits a code at the point where he wants git to remember the piece of code. Git then takes a snapshot of the code at the point where the user committed. You can think of it as a check point. In case you did something wrong you can always go back to the last commit where the project was working fine. 

There may be several reasons you may need git for, first is you may need git for projects you want to keep track of. Second is you may need git in case you want your thing to be uploaded to a cloud-based git repository like GitHub or Gitlab. 

Now comes the main part. 

# How to install git on Linux 

Since you already own a Linux machine so as you know, installing anything on Linux is fairly straight forward, you just need to type a few commands and it will install smooth and fast. So here you go. 

## Install Git on Debian/Ubuntu 

Git is available on the official Ubuntu and Debian repositories. Therefore, you can easily install it using APT: 

```
 sudo apt install git
``` 

# Install Git on Fedora 

You can install Git on Fedora using either DNF or YUM. If you're running an older version of Fedora (up to Fedora 21), use YUM: 

```
sudo yum install git
``` 

Conversely, if you have Fedora 22 or above running on your system, you can use DNF to install Git. 

```
sudo dnf install git
``` 

# Install Git on Arch Linux 

If you're on Arch Linux, you can install Git using Pacman: 

```
Sudo pacman –S git
``` 

# Install Git on FreeBSD 

To install Git on FreeBSD, issue the following command: 

```
sudo pkg install git
``` 

Once done, verify if the installation was successful by running the following command: 

```
git –version
``` 

You may get the following output (Your git version may be different) 

```
git version 2.34.1 
``` 

# How to configure git on Linux 

So you installed git and everything went well but wait its not over yet since some of its functionalities will not work like `push`, `pull`, etc. Except `clone`. For that all to work we need to configure Git. 

## Lets create an identity for git first 

So before committing anything, git may first require knowing your identity so that it can save commits based on it. Also, it may happen that more than one person will use git on your machine so in that case you can also set up different identity for different repositories. But first let's know how to set up a global identity. 

### To set a global identity, open the terminal and run the below commands: 

```
git config –global user.name “your_name”
``` 

```
git config –global user.email “your_email”
``` 

Now if you want to set up a default identity for a particular repository then get into that directory and type the following command: 

```
git config user.name “your_name”
``` 

```
git config user.email “your_email”
``` 

Now sometimes while pushing your repository to a cloud-based VCS like Github or Gitlab, you will be asked to enter your password of that GitHub or Gitlab account and there you may encounter problems. In that case you may either use a token or you can set up ssh keys. Both the ways are helpful.  

# Configure SSH for Git on Linux 

SSH helps the user in password-less logins.

That way, you don't have to enter your password every time you want to commit changes to a repository. 

```
ssh-keygen –t rsa –b 4096 –C “your_email_address”
``` 

You will be prompted to enter a location to save it. You can just press `ENTER` and let it save on default location. Similarly you will be prompted to `ENTER` a pass phrase, You can just press enter and proceed. 

You will get the following output: 

```
Generating public/private rsa key pair.  
Enter file in which to save the key (/default/location/.ssh/id_rsa):   
Enter passphrase (empty for no passphrase):   
Enter same passphrase again:   
Your identification has been saved in /default/location/  
Your public key has been saved in /default/location/id_rsa.pub  
The key fingerprint is:  
SHA256:<Your SSH key here> <your_email_address>  
The key's randomart image is: 

<Your SSH256 random art image here>  

``` 
  
Finally, you need to add the SSH key to the ssh-agent, which holds your system's private keys. For this, run the following code in the terminal: 

```
ssh-add ~/.ssh/id_rsa
``` 

## You can also change the default text editor for Git 

So, by default git uses vim text editor. But you can change it to any editor of your choice. I prefer `nano`. So, you can type the following command and change it: 

```
git config --global core.editor nano
``` 

# Let's review the configurations 

So now you have changed the configuration settings according to your preferences, it’s time to check if they are all correct. Type the following command: 

```
git config –list

``` 

At some point in the future, if you'd like to edit the configuration, open the gitconfig file by running: 

```
nano ~/.gitconfig
``` 

Then, edit the values of the identities that you want to change. 

# Finally running git on Linux

Now that you have successfully setup GitHub on your machine. Its time to make use of it and add Git to your workflow to better manage your projects.

If you like this post and want to deep dive in more of stuff like this, then be sure to checkout some related contents.

Thank You!
 

 

 

 
  
 