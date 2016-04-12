Prerequisites:

Minimum 1.9.4 version should be installed on the ansible master to execute the playbook.
passwordless ssh should be enabled from ansible master node to target node as root user. If root user is disabled then you will have to specify the sudo related details in inventory file

This playbook is written to setup cassandra on a single node and monitor it using graphite.

Update the name of your host in inventory file under cassy section and run the playbook as:

ansible-playbook -i inventory challenge.yml

This playbook will first install the java version 1.8, which is the prerequisite for cassandra. Then, it will install the cassandra package and make the required configurations. After that it will install and configure graphite to record stats of cassandra. At last it installs the apache and configures it to display graphite webpage.

To record the stats of cassandra a script has been created record_cassy.sh which records the statistics using nodetool command and sends it to graphite.
