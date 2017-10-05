```

#Report the latest available version of the API

[root@ip-172-31-13-246 ec2-user]# curl -u gastonorellana:cloudera 'http://localhost:7180/api/version'
v17

#Report the CM version

[root@ip-172-31-13-246 ec2-user]# curl -u gastonorellana:cloudera 'http://localhost:7180/api/v1/clusters'
{
  "items" : [ {
    "name" : "gastonorellana",
    "version" : "CDH5"
  } ]
}

#List all CM users

[root@ip-172-31-13-246 ec2-user]# curl -u gastonorellana:cloudera 'http://localhost:7180/api/v1/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "gastonorellana",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}

#Report the database server in use by CM

[root@ip-172-31-13-246 ec2-user]# curl -u gastonorellana:cloudera 'http://localhost:7180/api/v17/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false


  ```