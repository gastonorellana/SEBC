```

[root@ip-172-31-13-246 ec2-user]# curl -X POST -u gastonorellana:cloudera 'http://localhost:7180/api/v1/clusters/gastonorellana/services/hive/commands/stop'
{
  "id" : 1111,
  "name" : "Stop",
  "startTime" : "2017-10-05T14:25:01.910Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

[root@ip-172-31-13-246 ec2-user]# curl -X POST -u gastonorellana:cloudera 'http://localhost:7180/api/v1/clusters/gastonorellana/serviceshive/commands/start'
{
  "id" : 1117,
  "name" : "Start",
  "startTime" : "2017-10-05T14:26:09.365Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}


[root@ip-172-31-13-246 ec2-user]# curl -u gastonorellana:cloudera 'http://localhost:7180/api/v1/clusters/gastonorellana/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-13-246.us-west-2.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false

  
  ```