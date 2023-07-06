# Php website automated using an ansible playbook with the desired free SSL on the domain

This GitHub repository contains a playbook that enables easy deployment of a Git-based PHP website using an Nginx role. The playbook allows users to choose their desired SSL configuration by utilizing ACME validation and modifying the ACME directory.

## Playbook Description

The main playbook in this repository, main.yml, automates the process of deploying a PHP website hosted on Git to a remote server. The playbook utilizes the Nginx role and performs the following tasks:

1. Clones the Git repository containing the website contents to the remote server.
2. Copies the contents to the default document root directory, /var/www/html/{{ domain_name }}.
3. Restarts Nginx to enable Let's Encrypt validation.
4. Creates a directory structure for Let's Encrypt SSL certificates under /etc/nginx/ssl.
5. Generates an account key for the ACME module.
6. Generates a private key for the specified domain.
7. Generates a certificate signing request (CSR) with the domain name.
8. Performs the first challenge for the domain using the CSR and account key.
9. Creates the .well-known/acme-challenge directory for HTTP-01 challenges.
10. Copies the HTTP-01 challenges to the /.well-known/acme-challenge directory.
11. Performs the final Let's Encrypt verification and saves the full chain certificate file.
12. Activates SSL in the Nginx configuration file for the specified domain

### Sample video for prerequisites installation
***
I'm using amazon linux 2023 and I've installed the ansible using pip3
```
sudo yum install python3-pip git -y
sudo pip3 install ansible
```
A sample video has been made to guide you.

https://github.com/Chris-luiz-16/php-website-with-desired-free-ssl-using-ansible/assets/128575317/b05d30b1-15d4-4442-9291-392d0b88b837


