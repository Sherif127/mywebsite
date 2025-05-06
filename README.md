# 🌐 Website Deployment with Ansible on EC2 instance 

This project uses **Ansible** to automate the deployment of a simple website on an EC2 instance *amazon linux 2* server. It uses a modular Ansible **role** (`sherif-role`) to handle installation, configuration, and content deployment. The site is served using **Apache (httpd)** on a custom port (`88`) with all necessary security, SELinux, and firewall configurations.

---

## 📁 Project Structure


├── ansible.cfg
├── inventory
├── mywebsite.yml
├── README.md
├── sherif-role.zip
├── roles/
│ └── sherif-role/
│ ├── defaults/
│ │ └── main.yml
│ ├── files/
│ │ └── index.html
│ ├── handlers/
│ │ └── main.yml
│ ├── meta/
│ │ └── main.yml
│ ├── tasks/
│ │ └── main.yml
│ ├── templates/
│ │ └── motd.j2
│ └── vars/
│ └── main.yml

## ⚙️ Features
- Installs and configures **Apache (httpd)** on RHEL 9
- Deploys a custom `index.html` file
- Serves the website on custom port `88`
- Configures:
  - **SELinux** policies for non-standard port
  - **firewalld** to allow port 88
  - **Apache** to listen and serve on port 88
- Modular design using a single reusable Ansible role

🚀 How to Use
1. Clone the Repository
git clone https://github.com/mariam0o0/wordpress_ansible.git
2. Configure Inventory and Variables
Edit inventory.ini to define your target server under [webservers].
[webserver]
<EC2-PUBLIC-IP> ansible_user=ec2-user ansible_ssh_private_key_file=~/.ssh/your-key.pem
3. Set your custom port or any dynamic message for the template.
 roles/sherif-role/vars/main.yml
roles/sherif-role/defaults/main.yml
Set your custom port or any dynamic message for the template.

4. Run the Playbook
ansible-navigator run mywebsite.yml -i inventory -m stdout 
This will automatically install and configure Apache , Allow traffic on port 88 , Place your index.html at /var/www/html/ , Restart services and apply security configs
Once deployed, visit: your website

5. Don't forget to allow custom tcp port on security group

http://<EC2-PUBLIC-IP>:88

📚 Requirements
Ansible 2.10+
Python and pip3
RedHat-based target system with root or sudo access

Author:
Sherif Shaban
