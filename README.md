# README
This project installs a NGINX server as a Docker container in an Ubuntu box.
It creates self signed certificates for use by Nginx

## Dependencies
* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com)
* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
* Ansible Roles

        > angstwad.docker_ubuntu


##  Steps for starting WebServer

1.  Install required ansible roles stored in requirements.yml

```
cd provisioning
ansible-galaxy install -r requirements.yml
```

2.  Launch VM
`vagrant up`

3.  SSH to VM
`vagrant ssh`

4.  Confirm server has docker host and has created a container image
```
sudo docker version
sudo docker info
sudo docker images
```

5.  Deploy container in host
`sudo docker container run -p 80:80 --rm webhost:latest`





License
-------

BSD


Author Information
------------------

Lamberto Diwa



