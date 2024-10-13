# DB2 Ansible Scripts
This repo is a collection of different ansible playbooks in order to install and manage a db2 database. 

## Usage
These playbooks are general playbooks that can be used to help manage a IBM DB2 database environment. These are meant specifically for local/on-premise databases, they have not been tested for cloud environments. 

These may need to be modified to help fit into an environment. For example: your environment might not use port 50000 for TCP/IP connections for the db2_service_update.yml.

## Playbooks
Playbook Name | Playbook Type | Usage | Notes
:-- | :-- | :-- | :--
db2_install.yml | Installation | Install a new db2 database | Playbook assumes RHEL for OS and you will need to replace the "repository" variable to point to whatever repo you have with the db2 installation binary
db2_uninstall.yml | Installation | Removes Db2 databases and Db2 binaries | Helpful for decomming databases
db2_service_update.yml | Services | Updates the RHEL services for Db2 | Ensures TCP connectivity for port 50000
db2_utility_check.yml | Services | Checks for currently running database utilities | Checks for things such as backups, restores, re-orgs, re-indexes, etc. 
db2_get_install_dir.yml | Tasks | N/A | Contains a set of tasks, not meant fo execution. It gets the location of the db2 binary installations and version of DB2
db2_get_instance.yml | Instance Management | Gets all db2 instances on hosts machines | 
db2_instance_create.yml | Instance Management | Creates a new Db2 instance | 
db2_instance_drop.yml | Instance Management | Drops a Db2 instance | Deletes the instance
db2_instance_quiesce.yml | Instance Management | Quiesces the database instance | Places instances and all databases under the instance into a quiesced state
db2_instance_unquiesce.yml | Instance Management | Un-quiesces the database instance | Puts the database into a normal state
db2_instance_start.yml | Instance Management | Starts up an instance | Starts instance if not already active
db2_instance_stop.yml | Instance Management | Stops an instance | Stops an active instance
db2_database_activate.yml | Database Management | Activates the db2 database | Activating a Db2 database keep running even if there are no active connections
db2_database_deactivate.yml | Database Management |Deactivate the db2 database | Deactivate a Db2 database, database will still be connectable
db2_database_quiesce.yml | Database Management | Quiesces database | Database will be placed into maintenance modeand prevent non-admin connections
db2_database_unquiesce.yml | Database Management | Un-quiesces the database | Database will be placed into normal operations
db2_get_database.yml | Database Management | Pulls list of all local DB2 databases |
db2_get_hadr.yml | Database Management | Pulls all HADR nodes for the DB2 database | Useful for getting backup or reader DB2 nodes
db2_get_permissions.yml | User Management | Pull permission list of all users, groups, and roles | 
db2_users.yml | User Management |Get Db2 users list | 
