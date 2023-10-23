# YOLO Setup on Ubuntu Server 22.04

This Ansible playbook is designed to automate the setup of an e-commerce website and dashboard on an Ubuntu Server 22.04.

## Prerequisites

Before running this playbook, make sure you have the following prerequisites in place:

- An Ubuntu Server 22.04 machine.
- Ansible installed on your control machine.
- The necessary Ansible roles for this playbook, which include:
    - **vm-config**: This role handles general VM configuration.
    - **add-docker**: This role is responsible for installing and configuring Docker.
    - **clone-repo-run-docker-compose**: This role is used for cloning a Git repository and running Docker Compose for deploying an application.

## Usage

To use this playbook, follow these steps:

1. Clone this repository to your control machine.

2. Navigate to the directory containing this playbook.

3. Update the inventory file (typically `hosts`) to include the target server's IP address or hostname. Ensure that SSH access is set up and the target server is reachable.

4. Adjust any variables in the playbook or roles if needed. You can modify the `vars` section in the playbook to customize the configuration according to your requirements.

5. Run the playbook using the following command:

```bash
ansible-playbook -i hosts playbook.yml
```


## Playbook Details

Here's a breakdown of the key components of the playbook:

- `hosts`: Specifies the target server(s) where YOLO will be set up. Make sure to configure your inventory accordingly.

- `become: true`: Allows Ansible to become the superuser (root) during the execution of tasks.

- `remote_user: root`: Sets the remote user for SSH connections to "root."

- `gather_facts: true`: Gathers facts about the target system.

- `become_method: sudo`: Specifies that the `sudo` command will be used for privilege escalation.

- `become_user: root`: Sets the user to switch to when becoming the superuser.

- `become_flags: -H -S -n`: Flags for privilege escalation, which may be required depending on your system configuration.

- `ansible_python_interpreter: /usr/bin/python3`: Defines the Python interpreter to use during Ansible execution.

- `roles`: Lists the Ansible roles to be applied to the target system. In this case, we apply the `vm-config`, `add-docker`, and `clone-repo-run-docker-compose` roles.

## Contributing

If you'd like to contribute to this project, feel free to fork the repository, make your changes, and submit a pull request. We welcome any improvements or bug fixes.