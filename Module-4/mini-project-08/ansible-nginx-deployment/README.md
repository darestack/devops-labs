# Ansible Nginx Deployment

This Ansible playbook deploys and configures an Nginx web server on a target machine.

## Prerequisites

1.  **Ansible Control Node:** An Ubuntu machine with Ansible installed.
2.  **Managed Node:** An EC2 instance (or any other server) that you want to configure.
3.  **SSH Access:** The control node must have SSH access to the managed node using key-based authentication.

## Instructions

### 1. Create an Inventory File

Ansible needs an inventory file to know which hosts to connect to. Create a file named `inventory` in the same directory as the playbook with the following content:

```ini
[web_server]
your_server_ip ansible_user=your_username
```

Replace `your_server_ip` with the public IP address of your EC2 instance and `your_username` with the SSH username (e.g., `ubuntu` for an Ubuntu EC2 instance).

### 2. Run the Ansible Playbook

Execute the playbook using the following command:

```bash
ansible-playbook -i inventory deploy_nginx.yml
```

This command tells Ansible to use the `inventory` file to connect to the managed node and run the tasks defined in `deploy_nginx.yml`.

### 3. Verify the Deployment

Once the playbook has finished successfully, you can access the deployed website by navigating to `http://your_server_ip` in your web browser.

## Troubleshooting

### Nginx Reload Error

If you encounter an error like `Unable to reload service nginx`, it's likely due to a syntax error in the Nginx configuration. To debug this:

1.  SSH into the managed node:
    ```bash
    ssh your_username@your_server_ip
    ```

2.  Check the Nginx configuration for syntax errors:
    ```bash
    sudo nginx -t
    ```

3.  Review the Nginx service status and logs for more details:
    ```bash
    systemctl status nginx.service
    journalctl -xeu nginx.service
    ```
