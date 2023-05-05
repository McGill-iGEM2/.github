# We are McGill iGEM!
We do cool things with synthetic biology.

# Compute Canada
Command line is confusing so I'm creating a guideline document for everyone to follow :')
## Terminology
- Local: Anything you own, such as your personal compute and the files stored in it
- Remote: Anything on a network or machine outside of your personal network
- Cluster: A collection of computers that share some properties (e.g. location)
	- Computers within a cluster are interconnected and share the same file structure so you can access all your files on any computer within a cluster
- Node: A computer within a cluster
	- You will use one or more nodes when you submit or run a job on Compute Canada
- Shell/Terminal: The program/interface that lets you control the computer (local or remote) using only text-based commands (COMP206 ;) )
	- This is fundamental for using Compute Canada as there is no GUI 
## Creating a Profile
1) Register for an account [here](https://ccdb.alliancecan.ca/security/login) and make sure you use your McGill email
2) In order for undergraduates to have access to the alliance, we need to have a sponsor (Jasmin). You will be asked to enter his CCRI, which is `eaz-945-01`.
3) Once you submit the application, you will receive an email confirmation, which then notifies Jasmin that you would like to become a member of his project.
## Accessing the Server
You'll receive another email when Jasmin approves your membership. Under *My Account* $\rightarrow$ *My Resources and Allocations*, you should be able to see all of the available clusters. In total, we were given 4 allocations of 1 TB storage each.

`Beluga`, `Cedar`, `Narval`, and `Graham` are general purpose clusters with memory nodes and CPU/GPU allocation (which we were not given lol). `Niagara` is a cluster designed for large parallel jobs, which requires you to request access [here](https://ccdb.alliancecan.ca/services/opt_in)

Click Join, and you should be able to log into the `Niagara` cluster once you receive the confirmation email.

In order to access any cluster, you will need to `ssh` into it. As a quick overview, `ssh` is a communication protocol that enables two computers to commucation. In other words, this allows us to access another computer remotely through our own computer.

`ssh` Implementations:
Linux/macOS
- Available through the default command line applicatoin (search for terminal on your system)

Windows
- Available through the PowerShell terminal
- BUT I recommend using Windows Subsystem for Linux 2 (WSL 2)
	- This allows you to run the Linux environment on your computer (another OS)
	- Apparently bowtie2 only runs on Linux and macOS

### Using ssh
In order to ssh into a cluster, you will need to know (1) the name of the machine to which you want to connect, (2) your username and (3) your password.

- (1) The machine name will have the form `[cluster_name].computecanada.ca`
	- e.g. `cedar.computecanada.ca`
- (2) The username you created during registration
- (3) The password you created during registration

1) Open the terminal and enter the command shown below: 
	- When you connect to a remote machine for the first time, you will be asked to store a local copy of its "host key", which is a unique identifier that allows the SSH client to recognize the remote machine for future connections
	- The `-Y` flag enables you to run graphical applications on remote servers and display it on your local machine
2) Type `yes` when prompted to save the ssh key, then enter your password
3) Your ssh connection is successful when you see the following prompt in your terminal
	- `jts` is my username
	- `cedar1 ` is the login node
## How to transfer files
We will need a way to transfer files between the remote server and our local machine. Because we will all (most likely) be using the same data files (which are all MASSIVE and take forever to download), we should save them on the remote server for easy access. 

Personally, I use WinSCP

# Git
(Credit to my friend @notkaramel :'))
## Common commands for Git
>Make sure that you work on your branch and not on the `main` branch.

```bash
# Check the status of the repository.
# Attention to your current branch and files you modified/added.
# Attention to whether your branch(es) is behind/ahead of the GitHub repo.
git status

# Update the repository from remote repository
git pull

# Add all changes to the staging area
git add .  # or
git add -A
# Add a specific file to the staging area 
git add <file>

# Commit the changes in the staging area
git commit -m "Commit message"

# Push the changes to the remote repository
git push
```

## Checkout to your own branch
```bash
# Create a new branch
git checkout -b branch-name # replace branch-name with your own branch name

# For example:
git checkout -b emma
```

## Switch/Checkout to an existing branch
```bash
git checkout <branch name>	# or, on some machines
git switch <branch name>


# For example
git checkout main	# switch to main branch
git checckout emma	# switch to branch named "Emma"
```

