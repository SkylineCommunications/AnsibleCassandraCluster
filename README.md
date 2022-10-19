# Ansible Playbook: Install Cassandra Cluster (Debian)

With this playbook you can install and configure your first Cassandra cluster.
The supported operating system is all the system that are debian based (as we suggest the use of Ubuntu).

The playbook should be executed with elevated rights as some super user actions are needed for the installation.

Before running the playbook some variables need to be set in the variables.yml file.

## Before running the playbook

### Copy files

Copy all the files to the following location:
/home/ansible/install_cassandra

If the location doesn't exist, you can easily create it.

### Change the needed variables

In the variable folder, you'll find the variables.yaml file. Here you will need to change the following variables:
- clustername: set a custom clustername if wanted 
- seeds : add all the ip addresses that you want in the cassandra cluster (these should be the same as in the ansible hosts file)
- dc: dc location
- rack: location in rack

### Cassandra access

Standard the Cassandra root user will be configured with default password. It's advised to change this!
You can do this in the createRole.cql file in the cql folder. You can change the password there.

### Ansible hosts file

The playbook is configured to run all the hosts from [cassandra]. You can change this in the ansible hosts file, or change the hosts in the playbook.

## Running the playbook

Once everything is configured you can run the playbook with:
```bash
ansible-playbook install_Cassandra.yaml --ask-become-pass
```

## Improvement list

- dc and rack variable can be set for each node

## License

Code and documentation in this project are released under the [MIT License](https://github.com/SkylineCommunications/Skyline-DataMiner-Deploy-Action/blob/feature/preRelease/LICENSE.txt). 
