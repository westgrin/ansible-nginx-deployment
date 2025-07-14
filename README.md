# Mini Project - Deploy and Configure Nginx Web Server using Ansible

## Project Overview
This project automates the deployment and configuration of an Nginx web server on an Ubuntu server (54.227.3.228) using Ansible playbooks, building on previous Ansible and Terraform projects (Jul 8-14, 2025).

## Setup
- Initiated on Jul 14, 2025, 1:19 PM WAT.
- Used WSL Ubuntu, VS Code, and Git Bash in `/mnt/c/Users/User/Documents/Workspace/ansible-nginx-deployment`.
- System: 2 CPUs, 2GB free memory, 20GB free disk space.
- Target: AWS EC2 instance (Ubuntu 22.04, IP: 54.227.3.228).

## Execution Steps
1. **Confirm Prerequisites**:
   - Fixed AWS CLI error `InvalidGroup.NotFound` by creating `target-sg` in Terraform or using `default` security group.
   - Verified Ansible and SSH access to `ubuntu@54.227.3.228`.
   - Ensured security group allows TCP ports 22 and 80.
   - [Screenshot: `aws_instance_details_output_local.png` - Shows EC2 instance details.]
   - [Screenshot: `terraform_config_output_local.png` - Shows Terraform config.]
   - [Screenshot: `aws_security_group_output_local.png` - Shows security group rules.]
   - [Screenshot: `ansible_version_output_local.png` - Shows Ansible version.]
   - [Screenshot: `ssh_access_output_local.png` - Shows SSH to target.]
2. **Set Up Inventory**:
   - Created `inventory.ini` for Ubuntu target.
   - [Screenshot: `ansible_ping_output_local.png` - Shows ping response.]
3. **Install Nginx**:
   - Ran `install_nginx.yml` to install and start Nginx.
   - [Screenshot: `ansible_install_nginx_run_output_local.png` - Shows playbook run.]
4. **Configure Website**:
   - Ran `configure_nginx.yml` to deploy a custom website.
   - [Screenshot: `ansible_configure_nginx_run_output_local.png` - Shows playbook run.]
5. **Verify Deployment**:
   - Checked Nginx status and accessed `http://54.227.3.228`.
   - [Screenshot: `nginx_curl_output_local.png` - Shows curl output.]
   - [Screenshot: `nginx_website_output_local.png` - Shows browser page.]
   - [Screenshot: `nginx_verification_output_local.png` - Shows Nginx status and files.]
6. **Side Hustle Task**:
   - Automated playbooks with GitHub Actions.
   - Pushed to `https://github.com/westgrin/ansible-nginx-deployment`.
   - [Screenshot: `github_actions_ansible_run_local.png` - Shows workflow run.]
7. **Clean Up (Optional)**:
   - Created `cleanup_nginx.yml` to remove Nginx.
   - Destroyed EC2 instance (if applicable).
   - [Screenshot: `terraform_destroy_output_local.png` - Shows destroy output.]

## Learning Summary
This project enhanced my Ansible skills, building on user creation (Jul 14, 2025). It reinforced playbook creation and web server configuration.

## Tools Used
- **WSL Ubuntu Terminal**: For Ansible and SSH commands.
- **VS Code**: For editing playbooks and `README.md`.
- **Git Bash**: For GitHub operations.
- **GitHub Actions**: For automation.
- **Ansible**: For Nginx deployment.
- **Terraform**: For target node management.
- **AWS CLI**: For security group verification.

## Project Deliverables
- **Documentation**: This `README.md` with steps and learning summary.
- **Screenshots**:
  - `aws_instance_details_output_local.png`
  - `terraform_config_output_local.png`
  - `aws_security_group_output_local.png`
  - `ansible_version_output_local.png`
  - `ssh_access_output_local.png`
  - `ansible_ping_output_local.png`
  - `ansible_install_nginx_run_output_local.png`
  - `ansible_configure_nginx_run_output_local.png`
  - `nginx_curl_output_local.png`
  - `nginx_website_output_local.png`
  - `nginx_verification_output_local.png`
  - `github_actions_ansible_run_local.png`
  - `terraform_destroy_output_local.png` (if applicable)
- **Script Link**: [GitHub Repository](https://github.com/westgrin/ansible-nginx-deployment)

## Local Development Instructions
1. Clone repository: `git clone https://github.com/westgrin/ansible-nginx-deployment.git`
2. Install Ansible: `sudo apt install ansible -y`
3. Configure inventory: Edit `inventory.ini` with target details
4. Run playbooks: `ansible-playbook -i inventory.ini install_nginx.yml` and `configure_nginx.yml`
5. Verify: Access `http://54.227.3.228` in a browser

## Troubleshooting
- Fixed AWS CLI error `InvalidGroup.NotFound` by creating `target-sg` or using `default` security group.
- Ensured SSH access with `ssh ubuntu@54.227.3.228`.
- Verified security group allows TCP ports 22 and 80.
- Set DNS to `8.8.8.8` for network issues.
- Verified system resources with `lscpu`, `free -h`, `df -h`.

## Conclusion
This project successfully automated Nginx deployment and configuration, advancing my automation skills for web server management.