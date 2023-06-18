# Ansible Sync Script for Directory Synchronization using lsyncd in Docker Swarm

This repository contains an Ansible script that facilitates the synchronization of multiple directories using lsyncd within a Docker Swarm context. The script automates the installation, setup and configuration process, allowing for easy deployment and management of directory synchronization across a cluster of Docker Swarm nodes.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Introduction

In a Docker Swarm environment, there is often a need to keep certain directories in sync across multiple nodes. This can be challenging to achieve manually, especially when new nodes are added or existing nodes are removed from the cluster. The purpose of this Ansible script is to simplify the process of setting up and maintaining directory synchronization using lsyncd within a Docker Swarm context.

## Features

- Automates the installation and configuration of lsyncd on Docker Swarm nodes.
- Allows for the synchronization of multiple directories across the cluster.
- Supports dynamic scaling: easily adapts to changes in the Docker Swarm cluster.
- Facilitates centralized management and monitoring of directory synchronization.

## Prerequisites

Before using this Ansible script, ensure that the following prerequisites are met:

1. Docker Swarm cluster is set up and operational.
2. Ansible is installed on the control machine.

## Installation

To use this Ansible script, perform the following steps:

1. Clone this repository to your Ansible control machine.
2. To install lsyncd on every node in the cluster, run the following command:
   ```bash
   ansible-playbook -i inventory.yml -vv lsyncd/lsyncd-install.yml
   ```
   This will install lsyncd on every node in the cluster.
2. Modify the `inventory.yml` file to specify the target nodes in your Docker Swarm cluster.
3. Adjust the synchronization rules and options in the `lsyncd.conf.j2` file as per your requirements (if needed).

## Usage

1. Run the Ansible playbook using the command:
   ```bash
   ansible-playbook -i inventory.yml -vv lsyncd/lsyncdConfig.yml
   ```
   This will deploy and configure lsyncd on the specified Docker Swarm nodes.

2. Verify the synchronization by monitoring the logs or checking the synchronized directories on the target nodes.

## Configuration

The configuration for the synchronization process can be customized by modifying the `lsyncd.conf.j2` file. This file contains the synchronization rules and options that control how lsyncd operates. Adjust the rules and options according to your specific synchronization requirements.

Refer to the [lsyncd documentation](https://github.com/axkibe/lsyncd) for more information on configuring lsyncd.

## Contributing

Contributions to this project are welcome! If you find any issues or have suggestions for improvements, please feel free to submit a pull request or open an issue.

## License
This project is licensed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for details.