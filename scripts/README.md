# LLM_Bot Scripts Documentation

This README provides an overview of the scripts available in the `llm_bot/scripts` directory, their purpose, and how to execute them.

## Table of Contents

1. [Introduction](#introduction)
2. [Scripts Overview](#scripts-overview)
    - [create_folders_tree.ps1](#create_folders_treeps1)
    - [install_aws_cli.ps1 & install_aws_cli.sh](#install_aws_clip1--install_aws_clish)
    - [install_sam_cli.ps1 & install_sam_cli.sh](#install_sam_clip1--install_sam_clish)
    - [install_upgrade_python.ps1 & install_upgrade_python.sh](#install_upgrade_pythonp1--install_upgrade_pythonsh)
    - [install_upgrade_dependencies.ps1 & install_upgrade_dependencies.sh](#install_upgrade_dependenciesp1--install_upgrade_dependencyssh)
3. [Usage](#usage)

## Introduction

The `llm_bot` project involves creating a multichannel chat software. To assist in setting up the development environment and maintaining the project, several utility scripts have been provided in the `llm_bot/scripts` directory.

## Scripts Overview

### create_folders_tree.ps1

**Purpose:**  
This PowerShell script sets up the directory structure for the `llm_bot` project.

**How to Run:**  
From a PowerShell prompt, navigate to the `llm_bot/scripts` directory and execute:
```powershell
.\create_folders_tree.ps1

### install_aws_cli.ps1 & install_aws_cli.sh
**Purpose:**
These scripts (PowerShell for Windows, Bash for Linux/Mac) check if the AWS CLI is installed. If not, they will install it.

**How to Run:**

Windows:
From a PowerShell prompt, navigate to the llm_bot/scripts directory and execute:
powershell
Copy code
.\install_aws_cli.ps1
Linux/Mac:
From a terminal, navigate to the llm_bot/scripts directory and execute:
bash
Copy code
./install_aws_cli.sh
install_sam_cli.ps1 & install_sam_cli.sh
**Purpose:**
These scripts (PowerShell for Windows, Bash for Linux/Mac) are for installing the AWS Serverless Application Model (SAM) CLI.

**How to Run:**

Windows:
From a PowerShell prompt, navigate to the llm_bot/scripts directory and execute:
powershell
Copy code
.\install_sam_cli.ps1
Linux/Mac:
From a terminal, navigate to the llm_bot/scripts directory and execute:
bash
Copy code
./install_sam_cli.sh
install_upgrade_python.ps1 & install_upgrade_python.sh
**Purpose:**
These scripts (PowerShell for Windows, Bash for Linux/Mac) handle the installation and upgrading of Python and PIP to their latest versions.

**How to Run:**

Windows:
From a PowerShell prompt, navigate to the llm_bot/scripts directory and execute:
powershell
Copy code
.\install_upgrade_python.ps1
Linux/Mac:
From a terminal, navigate to the llm_bot/scripts directory and execute:
bash
Copy code
./install_upgrade_python.sh
install_upgrade_dependencies.ps1 & install_upgrade_dependencies.sh
**Purpose:**
These scripts (PowerShell for Windows, Bash for Linux/Mac) install and upgrade the Python dependencies for the project using the requirements.txt file located in the parent directory.

**How to Run:**

Windows:
From a PowerShell prompt, navigate to the llm_bot/scripts directory and execute:
powershell
Copy code
.\install_upgrade_dependencies.ps1
Linux/Mac:
From a terminal, navigate to the llm_bot/scripts directory and execute:
bash
Copy code
./install_upgrade_dependencies.sh
Usage
To use any of the scripts:

Navigate to the llm_bot/scripts directory.
Execute the desired script as per the instructions above.