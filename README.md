Omise Ansible Woocommerce
===

This is an Omise's mini project to demonstrate the usage of [Omise Woocommerce](https://github.com/omise/omise-woocommerce) by using [Digital Ocean](https://digitalocean.com) as a server. In this repo, we are going to be using these tools:
* [Ansible](http://www.ansible.com/)
* [Wordpress](https://wordpress.org)
* Wordpress Command Line Interface ([wp-cli](http://wp-cli.org))
* [Woocommerce](https://wordpress.org/plugins/woocommerce/) Plugin
* [Omise Woocommerce](https://github.com/omise/omise-woocommerce) Plugin

Don't be afraid if you do not know any of the above, but you're going to need a droplet for sure, make a registration [here](https://www.digitalocean.com/?refcode=5829ae33cb3c) if you haven't got one, login and create a droplet as an `Ubuntu 14.4x64` I'd reccommend you to go with the minimum plan as $5/month

Getting started
---------------

**0. Clone this repository**

Go into your workspace and use a shell command
```
git clone git@github.com:omise/omise-ansible-woocommerce.git
```

**1. create hosts file**

Go into `wordpress-ansible-woocommerce` folder, and create `hosts` file

```
touch hosts
```

edit `hosts` file by following this pattern

```
[name]
user@your.server.ip.address
```

where :
* `name` is your project name which should match with `playbook.yml` file i.g. I name this project "omise"
* `user` is your user on your digital ocean droplets i.g. I added a user on my machine as "ansible"
* `your.server.ip.address` is your ip address to your digital ocean droplets


**2. Change your configurations**

in `personal.yml` don't forget to put your droplet's ip to `your.server.ip.address`, which is your ip address to your digital ocean droplets
```
---
# mysql config
wordpress_db: wordpress
wordpress_db_user: wordpress
wordpress_db_password: password

# wordpress config
wordpress_url: your.server.ip.address
wordpress_user: admin
wordpress_user_email: foo@example.com
wordpress_password: root
wordpress_title: Omise Shop
```
and change other `username` / `email` / `password` as you may


**3. Use the magic command!**

```
ansible-playbook playbook.yml -i hosts -u user -K
```
where :
* `hosts` is your hosts file you just created
* `user` is your user on your digital ocean droplets i.g. I added a user on my machine as "ansible"

if you haven't got ansible installed on your machine, try this shell command 

```
brew install ansible
```
or following this [tutorial](https://valdhaus.co/writings/ansible-mac-osx/)

Any comments or questions are welcome, feel free to create an [issue](https://github.com/omise/omise-ansible-woocommerce/issues/new)
