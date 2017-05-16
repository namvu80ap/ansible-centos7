# Ansible playbook for install nginx, php7.1 run with Lumen or Ralavel

## Require:
1/ Vagrant and virtualbox
2/ Php Composer
3/ Ansible

## Test:
Create a Lumen or Larave blog project with composer command:
composer create-project --prefer-dist laravel/lumen blob

Config ansible vars: (config.yml)
#nginx config
nginx_root: /var/www/blog
nginx_root_doc: /var/www/blog/public
nginx_root_api: /var/www/blog
nginx_http_port: 80
nginx_server_name: localhost

####local config
source_code_folder: {{your_directory}}/blog/
admin_email: v_nam@yumemi.co.jp

## Start vagrant VM: ( default link port is localhost:8081, you can change the port in Vagrantfile )
vagrant up

## Run ansible-playbook:
ansible-playbook playbook.yml

## Test :
localhost:8081
