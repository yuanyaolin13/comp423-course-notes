# Setting up a dev container for Go

* Primary author: [Yuanyao Lin](https://github.com/yuanyaolin13)
* Reviewer: [Brian Liu](https://github.com/brianx426)

In this tutorial, we will set up a dev container for Go!

## Prerequisites
- [GitHub](https://github.com/) account and [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) installed
- [Docker](https://docs.docker.com/engine/install/) installed 
- [Visual Studio Code](https://code.visualstudio.com/) installed.

## Part 1: Setting up Project and initializing Git

First, you want to create a new directory within your computer.

For example, this project could reside in a folder within your Desktop or anything!
In this tutorial, I will name the directory `go-project`, but feel free to name it anything you need.

    mkdir go-project // to create the directory
    cd go-project    // to go into the directory

Then we can initialize Git in this folder by using this git subcommand in our directory:

    git init 

## Part 2: Instructions for creating a new Dev Container for Go

### Step 1: Create Container Configuration

Due to the nature of installations and varying coding environments, we want to set up a Dev Container for all of our Go needs in an isolated, aligned environment.

Lets begin!

1. In VS Code, we want to open the directory we created, in this case, `go-project`

2. Then, install **Dev Containers** in VSCode

3. Finally, create a `.devcontainer` directory in the root of project and then create a `devcontainer.json` file within that hidden directory like so

        .devcontainer/devcontainer.json

This JSON file allows you to define the configuration for the development configuration. Where we specify the following for the `devcontainer.json`:

    {
        "name": "go-project",
        "image": "mcr.microsoft.com/devcontainers/go:latest",
        "customizations": {
        "vscode": {
            "settings": {},
            "extensions": ["golang.Go"]
        }
        },
        "postCreateCommand": "go mod download"
    }

### Step 2: Creating module file

The next file we want to create is the `go.mod` file, this file defines the project's dependencies and is crucial to any Go project!

First, we want to run the command 

    go mod init <directory>

To initialize the go module within the root directory. In this case, we would run `go mod init go-project`!
Having completed this, we can go ahead and move on to the next step as we do not have any particular dependencies to add.

### Step 3: Reopen the Project in a VSCode Dev Container

This will initiate everything and allow us to use our Dev Container. To do this press `Cmd+Shift+P` (or `Control+Shift+P` on Windows) or you can press the search bar on the top middle of VSCode.
Then you want to type in "Dev Containers: Reopen in Container" to allow for the the Dev Container to be created. 

After this is done, in your terminal run: `go version` and something similar should pop up:

    vscode ➜ /workspaces/go-project $ go version 
    go1.23.4 linux/arm64

As a side note, this was created Jan 2025.

## Part 3: Creating Hello World in Go


## TEST
``` py linenums="1"
def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
```