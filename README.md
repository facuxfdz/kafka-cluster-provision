# Ansible Configuration Setup for Apache Kafka

This repository contains Ansible playbooks and configurations to set up Apache Kafka with custom properties and environment settings. The setup is organized into different playbooks to achieve a clean and structured configuration. You can use this README to guide you through the setup process.

## Prerequisites

Before running the Ansible playbooks, make sure you have the following prerequisites in place:

1. **Ansible**: Ensure Ansible is installed on your control machine where you plan to run the playbooks.

2. **Custom Configuration Files**: Prepare custom `server.properties` and `zookeeper.properties` files with your desired configurations. Place them in the `setup-properties` directory.

3. **User with Sudo Privileges**: Ensure you have a user with sudo privileges on the target machine. You will be prompted to enter the password for this user when you run the playbooks.

## Configuration Steps

Follow these steps to configure Apache Kafka with Ansible:
1. **Clone the Repository**: Clone this repository to your control machine.
2. **Customize the properties files**: Customize the `server.properties` and `zookeeper.properties` files in the `setup-properties` directory with your desired configurations.
2. **Run the main playbook**: Run the following command to run the main playbook:
    ```bash
    ansible-playbook --ask-become-pass main.yml
    ```
    This playbook will run the following playbooks in order:
    - `get-apache-kafka/site.yml`: This playbook will download Apache Kafka and Zookeeper from the official website.
    - `configure-env/site.yml`: This playbook will configure the environment for Apache Kafka and Zookeeper.
    - `configure-properties/site.yml`: This playbook will configure the properties for Apache Kafka and Zookeeper.

You will be prompted to enter the password for the user with sudo privileges on the target machine. Enter the password and press Enter to continue.  