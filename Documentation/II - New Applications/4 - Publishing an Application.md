Table of Contents

- [Publishing](<#publishing>)
	- [1. GitHub SSH Setup](<#1-github-ssh-setup>)
	- [2. Create New Repository](<#2-create-new-repository>)
	- [3. Download the elsciRL application template](<#3-download-the-elsciRL-application-template>)
	- [4. Change the git remote address](<#4-change-the-git-remote-address>)
	- [5. Commit and Push the Initial Setup](<#5-commit-and-push-the-initial-setup>)
	- [6. Develop Custom Environments](<#6-develop-custom-environments>)

---
# Publishing

A new application is defined when an environment has not been setup before. The easiest method for achieving this is to fork the elsciRL application template.

In this demonstration we upload the new application to a public GitHub repository and you should adapt this depending on your situation. For example, you can create a repository with a privately, on a different site such as GitLab or keep on a local hardware only.

## 1. GitHub SSH Setup
Before we create a new repository to upload our application to GitHub, we must first authenticate our account credentials to the local machine using an SHH key by following the guide in this link: [Connecting to GitHub with SHH - GitHub Docs](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).

## 2. Create New Repository
Simply create a blank repository with a suitable name, we don’t need any contents as they will be replaced by our first commit.

![GitHub New Repository](<./attachments/GitHub New Repository.png>)

![GitHub New Repository Created](<./attachments/GitHub New Repository Created.png>)

## 3. Download the elsciRL application template

Now we can download the template to our local machine using the following. Do this in whichever file directory you wish to save the application and results.

The general form of this is: ``git clone user/repository.git filename``

```bash
git clone https://github.com/pdfosborne/elsciRL-TEMPLATE.git elsciRL-GymFrozenLake 

cd elsciRL-GymFrozenLake
```

## 4. Change the git remote address

By default, the git remote address is for the template repository. This can be checked using the following command:

```bash
git remove -v
```

![Git Remote Address](<./attachments/Git Remote Address.png>)

The information on the new repository page provides the details we need but we don’t need to add an origin, rather change the address. So we can change this to our new on using the following:

```bash
git remote set-url origin git@github.com:pdfosborne/elsciRL-GymFrozenLake.git
```

## 5. Commit and Push the Initial Setup

```bash
git commit -a
git push
```

If you make no changes to the template before pushing then this will return an error that the main branch is already up to date and means a commit is not required.

![Git Initial Push](<./attachments/Git Initial Push.png>)

If you make any changes before trying to push a new screen will open in the terminal asking for the commit message, simply put “Initial setup commit” (or anything you prefer), CTRL-X to exit and save then ENTER to confirm this changes.

If the SSH authentication is setup correctly and the remote address is correct then the new repository will be updated with the template. Congratulations! We now have an application ready to customize.

## 6. Develop Custom Environments

Now the repository has been setup, you can edit the engine and environment setup to specify a new problem. Officially supported applications should adhere to the structure set by the template.