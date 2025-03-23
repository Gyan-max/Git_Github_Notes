# Introduction to Git and GitHub

Git is an open-source, distributed version control system created in 2005, primarily for tracking changes in code. GitHub, was founded in 2008, is a web-based platform that integrates with Git, enabling collaboration, version contril, and project hosting. 

While Git commands form the backbone of version control, GitHub enhances these features like ``Pull Requests``, and ``Issues Tracking``, often accessed via the web interface or GitHub CLI. 

 Key features include:

- **Distributed development**: Every developer has a full copy of the repository
- **Speed and efficiency**: Most operations are performed locally
- **Data integrity**: Ensures the cryptographic integrity of every bit of your project
- **Branching and merging**: Powerful tools for non-linear development
- **Staging area**: Intermediate area for selecting and preparing changes to commit


## Key Differences Between Git and GitHub

| Git | GitHub |
|-----|--------|
| Version control system | Web-based hosting service for Git repositories |
| Installed locally on your computer | Cloud-based service accessed via web browser |
| Works offline | Requires internet connection |
| Free and open-source | Free for public repositories, paid plans for private repositories |
| Command-line oriented | Graphical web interface |

## Basic Terminology

- **Repository (Repo)**: A storage location where your project files and revision history are kept
- **Commit**: A snapshot of changes made to files in the repository
- **Branch**: A parallel version of the repository that allows you to work on features separately
- **Merge**: The process of combining changes from one branch into another
- **Clone**: Creating a local copy of a remote repository
- **Pull**: Fetching changes from a remote repository and merging them into your local repository
- **Push**: Sending your committed changes to a remote repository
- **Fork**: Creating a personal copy of someone else's repository on GitHub
- **Pull Request**: Proposing changes from your fork to the original repository

# Version Control System

A ``Version Control System (VCS)`` is a tool or a software that helps in managing changes to files, code, or other digital content. It allows multiple perople to work on the same project simultaneously, track every modification, and keeps hostorical record of all changes. 

### **Key Features of Version Control System**
**1. Change Tracking** : Records who made what changes and when, providing a detailed history.

**2. Backup and Recovery** : Stores previous versions so that it can be recover easily states if something went wrong. 

**3. Collaborating** : Enables multiple contributors to work on the same project without overwrittiing each other's changes.

**4. Branching and Merging** : Allpws parallel development path (branches) that can laterly be combined (merged) into the main project.

**5. Conflict Resolution** : Help manage and resolve conflicting changes when multiple people edit the same file.


## Types of VCS 

**1. Local Version Control System** : Store version history on a single computer (*e.g, RCS*). Simple but limited to one user.

**2. Centralized Version Control System** : Use a central server to store all versions (*e.g, SVN, CVS*). Good for collaboration but reliant on the server. 

**3. Distributed Version Control System** : Each user has a full copy of the repository, including its history (*e.g, Git, Mercurial*). Offer flexiblity, offline work, and resillance. 

> **Git**, is a *Distributed version control system*, create in 2005 by **Linus Torvald** it is widly used for software development due to its speed, flexibility, and powerful features like branching and merging. When paired with platform like GitHub, it becomes a cornerstone for collaborative projects, allowing teams to share code, track issues, and manage releases. 


## Next Steps

Now that you understand the basics of Git and GitHub, proceed to [Installation and Setup](02-installation-setup.md) to get started with using these tools. 