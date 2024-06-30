# Windows 11 Dev Setup

## Select Your Operating System (OS)

1. Head to the official Microsoft website to [download Windows 11](https://www.microsoft.com/software-download/windows11)
2. Download the Windows 11 installation media creation tool. or the Windows 11 ISO file.
3. If you downloaded the ISO file, you can create a bootable USB drive using tools like [Rufus](https://rufus.ie/en/).
4. If you downloaded the installation media creation tool, run it and follow the on-screen instructions to create a bootable USB drive.
5. Go into your BIOS settings and set the USB drive as the primary boot device.(You can access the BIOS settings by pressing a specific key during startup, usually F2, F10, or Del).
6. Boot from the USB drive and follow the on-screen instructions to install Windows 11.
7. Once the installation is complete, update your new Windows 11 installation to ensure you have the latest security patches and drivers.

## Install a Text Editor or Integrated Development Environment (IDE)

1. Head to the official Visual Studio Code website to [download Visual Studio Code](https://code.visualstudio.com/)
2. It will automatically detect your operating system and provide you with the appropriate download link.
3. Click on the download link to download the Visual Studio Code installer. In this case, it will be the Windows 64-bit version.
4. Once the download is complete, run the installer by double-clicking on the downloaded file.
5. Follow the on-screen instructions to install Visual Studio Code on your Windows 11 system.
6. Once the installation is complete, open Visual Studio Code to configure any settings or extensions as needed for your development workflow.
7. You can use the windows package manager `ẁinget` to install Visual Studio Code by running the following command: `winget install --id Microsoft.VisualStudioCode`

## Set Up Version Control System

1. Head to the official Git website to [download Git](https://git-scm.com/download/win)
2. Download the Git installer for Windows.(64-bit or 32-bit, depending on your system).
3. Run the installer by double-clicking on the downloaded file.
4. Follow the on-screen instructions to install Git on your Windows 11 system.
5. Verify the installation by opening Command Prompt and running the following command: `git --version`
6. You can use the windows package manager `ẁinget` to install git by running the following command: `winget install --id Git.Git -e --source winget`

### Create a GitHub Account

1. If you don't already have a GitHub account, head to the official GitHub website to [create a GitHub account](https://github.com/)
2. Click on the "Sign up" button and follow the on-screen instructions to create your GitHub account.
3. Complete the account creation process by verifying your email address.
4. You can now use your GitHub account to host your repositories and collaborate with others.

### Configure Git

1. Open Git Bash or Command Prompt and configure Git with your name and email address using the following commands: `git config --global user.name "Your Name"` `git config --global user.email "your.email@gmail.com"`
2. Its a good idea to set up a credential manager to avoid entering your username and password every time you interact with a remote repository. You can do this by running the following command: `git config --global credential.helper manager`
3. Its time to initialize a new Git repository for your project. Navigate to the project directory in Command Prompt or Git Bash and run the following command: `git init`
4. Add your files to the staging area and commit them using the following commands: `git add .` `git commit -m "Initial commit"`
5. Create a new repository on GitHub and push your local repository to the remote repository using the following commands: `git remote add origin <repository-url>` `git push -u origin <branch-name>`
6. You can now manage your project's version control using Git and GitHub.

## Install Necessary Programming Languages and Runtimes

### Install Python

1. Head to the official Python website to [download Python](https://www.python.org/downloads/)
2. Download the latest source release of Python for Windows.
3. Run the installer by double-clicking on the downloaded file.
4. Follow the on-screen instructions to install Python on your Windows 11 system.
5. Verify the installation by opening Command Prompt and running the following command: `python --version`
6. You can use the windows package manager `ẁinget` to install Python by running the following command: `winget install --id Python.Python`

#### Install Package Managers (pip)

1. Head to the official Python website to [download pip](https://pip.pypa.io/en/stable/installation/)
2. Download the `get-pip.py` script by right-clicking on the link and selecting "Save link as..."
3. Run `py get-pip.py` in the command prompt to install pip.
4. Alternatively, use the 'ensurepip' module that comes with Python to install pip by running the following command: `py -m ensurepip --upgrade`

### Install a MYSQL Database

1. Head to the official MySQL website to [download MySQL](https://dev.mysql.com/downloads/windows/installer/5.7.html)
2. Download the MySQL installer for Windows.
3. Run the installer by double-clicking on the downloaded file.
4. Follow the on-screen instructions to install MySQL on your Windows 11 system.
5. Select "Full" or "Custom" installation to install MySQL Server, MySQL Workbench, and other necessary components.
6. Configure MySQL by setting up a root password and creating a new user with the necessary privileges for your project.
7. Verify the installation by connecting to the MySQL server using the following command: `mysql -u root -p`
8. You can also use the windows package manager `ẁinget`.

## Set Up Development Environments and Virtualization (Optional)

### Install Docker Desktop

#### Prerequisites

1. Windows 11 Pro, Enterprise, or Education (Home edition does not support Hyper-V)
2. 64-bit processor with Second Level Address Translation (SLAT)
3. 4GB system RAM
4. Virtualization technology enabled in BIOS/UEFI
5. Windows Subsystem for Linux 2 (WSL 2) enabled
   - Open PowerShell as Administrator and run the following command: `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`,
`dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`, and restart your computer.

- Update WSL
  - Download the WSL Linux from the Microsoft Store.
  - Set WSL 2 as the default version by running the following command in PowerShell: `wsl --set-default-version 2`

#### Installation

1. Head to the official Docker website to [download Docker Desktop](https://www.docker.com/products/docker-desktop)
2. Downlaod the Docker Desktop installer for Windows.
3. Run the installer by double-clicking on the downloaded file.
4. Follow the on-screen instructions to install Docker Desktop on your Windows 11 system.
5. Configure Docker settings and create containers for your development environment as needed.
6. Verify the installation by running the following command in the command prompt: `docker --version`

## Explore Extensions and Plugins

1. Explore available extensions, plugins, and add-ons for Visual Studio Code to enhance functionality, such as syntax highlighting, linting, code formatting, and version control integration.
2. Install extensions like:
   - Python
   - GitLens
   - ESLint
   - Prettier
   - Docker
   - SQLTools MySQL/MariaDB/TiDB
   - Database Client
   - Remote - WSL (if using WSL 2 with Linux)
   - Code Runner
   - etc. as needed for your development workflow.

## winget Package Manager

- Windows Package Manager (winget) is a command-line tool that allows you to discover, install, upgrade, remove, and configure applications on Windows 10 and Windows 11.

 1. Open PowerShell as Administrator.
 2. **VS Code**: `winget install --id Microsoft.VisualStudioCode`
 3. **Git**: `winget install --id Git.Git`
 4. **Python**: `winget install --id Python.Python.3.11`
 5. **MySQL**: `winget install -e --id Oracle.MySQL`
 6. **Docker Desktop**: `winget install -e --id Docker.DockerDesktop`
 7. **Github Desktop**: `winget install -e --id GitHub.GitHubDesktop`
 8. **Node.js**: `winget install --id OpenJS.NodeJS`

- Find more packages by running `winget search <package-name>`
-

## Challenges and Solutions

1. **BIOS Settings**: Accessing the BIOS settings to set the boot device can be challenging for some users. Refer to your system's manual or manufacturer's website for specific instructions on how to access the BIOS settings.
2. **Git Configuration**: Configuring Git with your name and email address can be confusing. Refer to the official Git documentation for detailed instructions on how to configure Git. (consider using the `git config --global --edit` command to open the configuration file in a text editor for easier editing.) or opt for ssh keys for authentication.
3. **Python Installation**: Installing Python and setting up the PATH variable can be tricky. Make sure to check the box that says "Add Python to PATH" during the installation process.
4. **MySQL Configuration**: Configuring MySQL with the root password and user privileges can be complex. Refer to the MySQL documentation for detailed instructions on how to set up MySQL.
5. **Docker Installation**: Installing Docker Desktop on Windows 11 can be challenging due to system requirements and dependencies. Make sure to check the prerequisites and follow the installation instructions carefully.
6. **Visual Studio Code Extensions**: Installing and managing extensions in Visual Studio Code can be overwhelming. Take your time to explore and install extensions that suit your development workflow.
7. **WSL 2 Installation**: Setting up Windows Subsystem for Linux 2 (WSL 2) can be tricky. Follow the official Microsoft documentation for detailed instructions on how to enable and configure WSL 2 on Windows 11.

## Links

- [Windows 11 Download](https://www.microsoft.com/software-download/windows11)
- [Visual Studio Code Download](https://code.visualstudio.com/)
- [Git Download](https://git-scm.com/download/win)
- [Python Download](https://www.python.org/downloads/)
- [MySQL Download](https://dev.mysql.com/downloads/windows/installer/5.7.html)
- [Docker Desktop Download](https://www.docker.com/products/docker-desktop)
- [Initialized Git Repository](https://github.com/Gideon-Yebei/Dev_Setup)
