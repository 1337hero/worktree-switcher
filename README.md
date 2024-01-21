# Git WorkTree (gwt) Switcher
<p align="center">
  <a href="https://gulpjs.com">
    <img height="325" width="325" src="logo.png">
  </a>
  <p align="center">Streamline Your Git Workflow</p>
</p>

## What is gwt ?

If you're familiar with git worktrees, you might have experienced the hassle of having to `cd` into each folder just to switch branches. It can be quite a tedious process, right?

Well, say hello to the gwt switcher! It's like having a magic wand to quickly hop between different worktrees in your Git projects.

With just a simple and straightforward command, you can jump directly into the worktree of any branch you're working on within a project. No more shuffling through directories!

### **Prerequisites**
- Basic knowledge of Git and your terminal enviroment.
- Git Worktree must be properly set up and used in the project.
- Bash or Zsh shell environment.

### **Installation**
To get started with the gwt switcher, you'll need to integrate it into your shell environment. Here's how you can set it up:

1. **Define the Function:**
   - Open your shell configuration file using a text editor. This file is typically named `.bashrc` for Bash or `.zshrc` for Zsh. You'll find it in your home directory.
   - Copy and paste the `gwt` function code into this file. This step ensures that the function is loaded and ready to use every time you open your terminal.

2. **Apply the Changes:**
   
   For the changes to take effect, you need to reload your shell configuration. You can do this in two ways:
    - **Option 1:** Source your configuration file directly in the terminal. This is like a quick refresh for your shell settings.
     
     ```
     source ~/.bashrc  # If you're using Bash
     source ~/.zshrc   # If you're using Zsh
     ```
    - **Option 2:** Close and reopen your terminal. This naturally re-loads your configuration file.

3. **Advanced Setup (Optional):**
    - If you maintain a dotfiles repository for your configuration files, you might prefer keeping the `gwt` function in a separate file and sourcing it from your shell configuration.
    - First, clone this repository into your dotfiles:
    ```
    git clone <repository-url> ~/dotfiles/
    ```
    - Then, import the `gwt` function from the .wt-switch file into your shell configuration by adding the following line to your `.bashrc` or .`zshrc:`
    ```
    source ~/dotfiles/worktree-switcher/.wt-switch
    ```
    - This keeps your configuration organized and makes it easy to update the function by simply pulling changes into your dotfiles repository.

By following these steps, you'll have the `gwt` switcher ready to go, making worktree management a breeze!

## Configuration
To configure the gwt utility for use with multiple projects, perform the following steps:

1. **Create a .gwtconfig File:**
- In the root directory of your workspace where multiple projects are located, create a ``.gwtconfig`` file.
- This file should contain the absolute path to the directory that serves as the root for all your projects containing worktrees.

2. **Specify the Projects Root Directory:**
- Inside the `.gwtconfig` file, write the absolute path to the root directory of your projects. This is where `gwt` will start searching for the worktrees.
- Ensure the path is correct and does not end with a slash (/).

For example, if your projects are located in `/Users/Username/Sites/` and each project within this directory has its own set of worktrees, the `.gwtconfig` should contain:

```
/Users/Username/Sites/
```

## Usage
To switch to a worktree associated with a specific branch within a project, use the `gwt` command followed by the project name (the directory name within the root projects directory) and the branch name:

```
gwt <project-name> <branch-name>
```

## Examples:
Switch to the `feature/new-ui` branch's worktree in the `my_project` project located under `/Users/Username/Sites/my_project`:

```
gwt my_project feature/new-ui
```

Switch to the `dev` branch's worktree in the `website_project` located under `/Users/Username/Sites/website_project`:

```
gwt website_project dev
```

Remember, the `gwt` command format is `gwt <project-name> <branch-name>`, where `<project-name>` is the directory name of the project within your projects root directory, and `<branch-name>` is the name of the branch whose worktree you wish to navigate to.

## Troubleshooting
- **Worktree Does Not Exist:** Verify the branch name is correct and a worktree for that branch exists within the specified project.

- **Configuration File Not Found:** Ensure that a `.gwtconfig` file is present in the project's root directory and that it contains the correct project path.

- **Permission Issues:** Ensure that you have the necessary permissions to navigate to and modify the contents of the worktree directories.

Contributing to Git WorkTree Switcher
We welcome contributions from the community! Whether you're fixing bugs, improving the documentation, or proposing new features, your help is appreciated. Here's how you can contribute:

### Reporting Issues
If you encounter any bugs or issues, please report them by creating an issue in the project's issue tracker. Provide as much detail as possible, such as:

- A clear and descriptive title.
- Steps to reproduce the issue.
- Expected behavior and actual behavior.
- Screenshots or logs if applicable.

### Suggesting Enhancements
We're always looking for suggestions to improve Git WorkTree Switcher. If you have an idea for a new feature or an enhancement, please:

- Open an issue and tag it as a feature request.
- Describe the feature in detail and explain how it benefits the users.
- Consider whether your feature can be implemented in a way that is consistent with the project's existing style and architecture.

### Submitting Changes
If you'd like to contribute code, please follow these steps:

1. Fork the repository.
2. Clone your fork to your local machine.
3. Create a new branch for your changes.
4. Make your changes and test them thoroughly.
5. Commit your changes with clear and descriptive commit messages.
6. Push your changes to your fork on GitHub.
7. Open a pull request against the main repository. In your pull request, include: 
   - A clear and descriptive title.
   - A description of the changes and why they are necessary.
   - Any relevant issue numbers.
8. Await review. Be open to feedback and willing to make changes if requested.
