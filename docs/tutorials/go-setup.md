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

This JSON file allows you to define the configuration for the development configuration.

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