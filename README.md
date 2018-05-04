# README
This project installs a NGINX server as a Docker container in an Ubuntu box.
It creates self signed certificates for use by Nginx

## Dependencies
* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com)
* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
* Ansible Roles
    * [angstwad.docker_ubuntu](https://github.com/angstwad/docker.ubuntu)
*  Setup self-signed certificates.  Follow instructions [here](https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-nginx-in-ubuntu-16-04)


##  Steps for starting WebServer

1.  With Ansible installed (~>2.0).  Install required ansible-galaxy roles using requirements.yml.

```
cd provisioning
ansible-galaxy install -r requirements.yml
```

2.  Launch VM using Vagrant.  Vagrant will provision the host server via Ansible.  It will install Docker host, create a container image and install Self-Signed Certificates.  Server is accessible via private ip 192.168.153.54.
`vagrant up`

3.  SSH to VM
`vagrant ssh`

4.  Confirm server has docker host and has created a container image.
    ```
    sudo docker version
    sudo docker info
    sudo docker images
    ```

alternatively do `gpasswd -a vagrant docker` to have sudo access


5.  Deploy container in host.
`sudo docker container run -p 80:80 --rm webhost:latest`

6.  Access the site "192.168.153.54"



License
-------

BSD


Author Information
------------------

Lamberto Diwa



