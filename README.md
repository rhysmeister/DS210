# DS210
Provides a few VMs for the Datastax Academy DS210 Course - https://academy.datastax.com/resources/ds210-datastax-enterprise-6-operations-with-apache-cassandra

Provides the following VMs

ds210-node1
ds210-node2
ds210-node3

With the DSE software stack installed. No further configuration is performed (That's your job).

The vault.yml file, excluded by .gitignore, should contain the two following variables...

datastax_username
datastax_password

These are login details for Datastax Academy. This is of course encrypted by vault. Vagrant will prompt for the password.
