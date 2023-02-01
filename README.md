# PackerDB

## About

This project demonstrates the configuration of an AMI (Amazon Machine Image) with _Packer_ ([see script here](./packer.json)). The _packer_ file defines the configuration steps for AWS to take when creating the AMI, it also includes any provisioning scripts that are required for any instances.

## Provisioners

### MongoDB - script

[Here](./env/mongodb/script.sh) is the provisioning script used to install MongoDB on any new instances. This script will download the GPG Keys, add the MongoDB repo, and then download and install MongoDB. Then it will configure the base settings by creating a _symbolic link_ to our custom `mongod.conf` file.

### MongoDB - conf

[Here](./env/mongodb/mongod.conf) is the mongod.conf file which binds our MongoDB installation to the `0.0.0.0` address.

## Variables

The project uses `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` to enable packer to connect to our AWS account and authenticate jobs.
