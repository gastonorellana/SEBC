```


[root@ip-172-31-13-246 ec2-user]# curl -u gastonorellana:cloudera 'http://localhost:7180/api/v2/cm/deployment'
{
  "timestamp" : "2017-10-05T14:15:09.824Z",
  "clusters" : [ {
    "name" : "gastonorellana",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "3193962496"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "319396249"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false"
          }, {
            "name" : "hiveserver2_java_heapsize",
            "value" : "3193962496"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "1764307763"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "296"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-13-246.us-west-2.compute.internal"
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "Cloudera$01"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-fbcc04853814e1ae4a9db47392b8cf20",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "dd9fab53-9fab-40b0-9b72-e7e8d10edefd"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-fbcc04853814e1ae4a9db47392b8cf20",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "dd9fab53-9fab-40b0-9b72-e7e8d10edefd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1u06icc6rn2nezafdha8g0p97"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-fbcc04853814e1ae4a9db47392b8cf20",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "dd9fab53-9fab-40b0-9b72-e7e8d10edefd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3xuk1xkpwif2h9f24r1uaandy"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true"
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-46a0a89f4dd4bfb05c29da2d51d6dac6",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "0002cd87-89bb-49c4-bec7-ee7bb575e5e0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2g0jd383daalqr96flfi307ue"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-b23cfadd909effa426096c8038cbdf13",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "11653a56-8874-4cfb-b4b1-3bfc32f43b20"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "avrz9ja6pu3oqi08qm2y1xdwi"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-fbcc04853814e1ae4a9db47392b8cf20",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "dd9fab53-9fab-40b0-9b72-e7e8d10edefd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "49k1nh1fzp8be8w3fcnu5u5h9"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HUE_SERVER",
          "items" : [ {
            "name" : "hue_http_port",
            "value" : "18888"
          } ]
        } ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-13-246.us-west-2.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "Cloudera$01"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-186b39ca52d108dae7d4904e14883268"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-186b39ca52d108dae7d4904e14883268",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "71d4bc9a-f0f9-4ae4-9aaa-c56f912d0cd6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ewdtth9op5s6ho7ddarjk7ofy"
          }, {
            "name" : "secret_key",
            "value" : "CdFBAz9mWj8GlwQXceYQNmRzelGJ8L"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-186b39ca52d108dae7d4904e14883268",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "71d4bc9a-f0f9-4ae4-9aaa-c56f912d0cd6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d99ucrscm9bowras76xnllu4n"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-13-246.us-west-2.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "Cloudera$01"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-186b39ca52d108dae7d4904e14883268",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "71d4bc9a-f0f9-4ae4-9aaa-c56f912d0cd6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "98pcux9n8w0zwzunq0nzyd6xh"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "16"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm,/disk01/yarn/nm,/disk02/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs,/disk01/yarn/container-logs,/disk02/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "2825"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "15447"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "6"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "QtI2Jd5Vce818f6KWWOnYI65hQrtKO"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-b23cfadd909effa426096c8038cbdf13",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "11653a56-8874-4cfb-b4b1-3bfc32f43b20"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "74cf7i7qj3f5euzgqzmnaqg4i"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-186b39ca52d108dae7d4904e14883268",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "71d4bc9a-f0f9-4ae4-9aaa-c56f912d0cd6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cyebg3cb60ekt5qgerby0x2n6"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-46a0a89f4dd4bfb05c29da2d51d6dac6",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "0002cd87-89bb-49c4-bec7-ee7bb575e5e0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bl7rup7lkr9xzc7wexscn1wv5"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-b23cfadd909effa426096c8038cbdf13",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "11653a56-8874-4cfb-b4b1-3bfc32f43b20"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4wvg38myoryovdcqhoplr0qt8"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-fbcc04853814e1ae4a9db47392b8cf20",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "dd9fab53-9fab-40b0-9b72-e7e8d10edefd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8j0h62blin9foljawmd2v413c"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-46a0a89f4dd4bfb05c29da2d51d6dac6",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "0002cd87-89bb-49c4-bec7-ee7bb575e5e0"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "47"
          }, {
            "name" : "role_jceks_password",
            "value" : "1ec33ktk7is1irhjidyw6adk4"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/disk01/dfs/dn,/disk02/dfs/dn"
          }, {
            "name" : "dfs_datanode_bind_wildcard",
            "value" : "true"
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/disk01/dfs/jn"
          }, {
            "name" : "journalnode_bind_wildcard",
            "value" : "true"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn,/disk01/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_bind_wildcard",
            "value" : "true"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "3193962496"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "3193962496"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "yxdToa1wji5JpQNKi7KFaioDn0HjDU"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "fGEW5xOpJWgYACH9ewlHbOu7rGHrlA"
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos"
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "C3g3vvdalQgMde7icPNIBW5MvqoVa3"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-46a0a89f4dd4bfb05c29da2d51d6dac6",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "0002cd87-89bb-49c4-bec7-ee7bb575e5e0"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-186b39ca52d108dae7d4904e14883268",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "71d4bc9a-f0f9-4ae4-9aaa-c56f912d0cd6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ab141tn8zmhjnd4k4sxb4ulg8"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-46a0a89f4dd4bfb05c29da2d51d6dac6",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "0002cd87-89bb-49c4-bec7-ee7bb575e5e0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "t3q8p6tgc08gjs1dov1rvv6e"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-b23cfadd909effa426096c8038cbdf13",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "11653a56-8874-4cfb-b4b1-3bfc32f43b20"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c8l3k01o4wnvybi4x3peojsqs"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-fbcc04853814e1ae4a9db47392b8cf20",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "dd9fab53-9fab-40b0-9b72-e7e8d10edefd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bk67se3mwyz4p8n82s409a42s"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-b23cfadd909effa426096c8038cbdf13",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "11653a56-8874-4cfb-b4b1-3bfc32f43b20"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8y78qf2rzwpz7n78xm58xj31r"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-fbcc04853814e1ae4a9db47392b8cf20",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "dd9fab53-9fab-40b0-9b72-e7e8d10edefd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9nsgphpbcuvnlwhr3zd86rtab"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-186b39ca52d108dae7d4904e14883268",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "71d4bc9a-f0f9-4ae4-9aaa-c56f912d0cd6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5bbn3wja2uz2rb72ly3l3rcik"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-46a0a89f4dd4bfb05c29da2d51d6dac6",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "0002cd87-89bb-49c4-bec7-ee7bb575e5e0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "amo7msks2ar2l4azbmzjwrm82"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-b23cfadd909effa426096c8038cbdf13",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "11653a56-8874-4cfb-b4b1-3bfc32f43b20"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2a30k26bbxpwsbsysqz6ps0o6"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-fbcc04853814e1ae4a9db47392b8cf20",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "dd9fab53-9fab-40b0-9b72-e7e8d10edefd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1w11wuz89u112t4527vzn55is"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-b23cfadd909effa426096c8038cbdf13",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "11653a56-8874-4cfb-b4b1-3bfc32f43b20"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "55"
          }, {
            "name" : "role_jceks_password",
            "value" : "62xhyrjw1w4u1w76laa34qvoy"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-fbcc04853814e1ae4a9db47392b8cf20",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "dd9fab53-9fab-40b0-9b72-e7e8d10edefd"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "49"
          }, {
            "name" : "role_jceks_password",
            "value" : "64395v5tp1hasoldq54rwbyec"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SENTRY_SERVER",
          "items" : [ {
            "name" : "sentry_server_java_heapsize",
            "value" : "268435456"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ip-172-31-13-246.us-west-2.compute.internal"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "Cloudera$01"
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,bootcamp"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-SENTRY_SERVER-46a0a89f4dd4bfb05c29da2d51d6dac6",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "0002cd87-89bb-49c4-bec7-ee7bb575e5e0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dzchc5ut6d35khe91shvihppd"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "0002cd87-89bb-49c4-bec7-ee7bb575e5e0",
    "ipAddress" : "172.31.11.232",
    "hostname" : "ip-172-31-11-232.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "71d4bc9a-f0f9-4ae4-9aaa-c56f912d0cd6",
    "ipAddress" : "172.31.13.151",
    "hostname" : "ip-172-31-13-151.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "8979f704-3298-4272-924f-d728353dba05",
    "ipAddress" : "172.31.13.246",
    "hostname" : "ip-172-31-13-246.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "dd9fab53-9fab-40b0-9b72-e7e8d10edefd",
    "ipAddress" : "172.31.13.83",
    "hostname" : "ip-172-31-13-83.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "11653a56-8874-4cfb-b4b1-3bfc32f43b20",
    "ipAddress" : "172.31.7.199",
    "hostname" : "ip-172-31-7-199.us-west-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-d63a650ac783cd8ead8a66992a9bc2ee",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "a2dbb36029ecad81cdb7078f8ca193f3bf53480d8f256c3f4a694e2fd309e93d",
    "pwSalt" : -6480742040598110543,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-d63a650ac783cd8ead8a66992a9bc2ee",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "b240047e9e6d37394f8973b4682bef2db9b827071bb0aaddf02c4853a510a385",
    "pwSalt" : 3634904566937357205,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-d63a650ac783cd8ead8a66992a9bc2ee",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "a767eabeb210cbcd27f97b35ccc7b0804cd3c0c944ea377ffd8b1832f2b47e82",
    "pwSalt" : 7407291411704417065,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-d63a650ac783cd8ead8a66992a9bc2ee",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "2c2ebb83b8161a1b9cdd88a4de62f3cef1cad9cd8124305e649ab52035546ac7",
    "pwSalt" : -5742507874387317404,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-d63a650ac783cd8ead8a66992a9bc2ee",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c6a51d5f6b40755ecf4d45f2650935482fdb5dfecd1436d6cbc0fdca064823f4",
    "pwSalt" : 6900882322913153974,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "220e4af157e33d88a611ab210feeb151d183911b386c45ec44434bed11b2a485",
    "pwSalt" : 7569466227310385680,
    "pwLogin" : true
  }, {
    "name" : "gastonorellana",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "65535537c7cea0fd5682f7d7abbfa671889800e3d213255c43b2b2f32741f9e7",
    "pwSalt" : 4963251956203268903,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "fe58c76021f9b68fcdcdf9ea58c5527d9b59f52afbb0ce09461274aa8555f91e",
    "pwSalt" : 2063575051861131307,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.11.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170811-0014",
    "gitHash" : "3c3ea33a12076fb83a8f11c4452c52fac685d01b",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "ACTIVITYMONITOR",
        "items" : [ {
          "name" : "firehose_database_host",
          "value" : "ip-172-31-13-246.us-west-2.compute.internal"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "Cloudera$01"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        }, {
          "name" : "firehose_storage_dir",
          "value" : "/var/log/cloudera-host-monitor"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-13-246.us-west-2.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "Cloudera$01"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        }, {
          "name" : "firehose_storage_dir",
          "value" : "/var/log/cloudera-service-monitor"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-d63a650ac783cd8ead8a66992a9bc2ee",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "8979f704-3298-4272-924f-d728353dba05"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "15345won45tgjtcg3r35q0zps"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-d63a650ac783cd8ead8a66992a9bc2ee",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "8979f704-3298-4272-924f-d728353dba05"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "80jy5lm9sp66ynznadt1wctmm"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-d63a650ac783cd8ead8a66992a9bc2ee",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "8979f704-3298-4272-924f-d728353dba05"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2nc8js2fv5vb7ciqqk4xvr9ku"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-d63a650ac783cd8ead8a66992a9bc2ee",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "8979f704-3298-4272-924f-d728353dba05"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "7kpm4ky6cnvxcnn0oco0qsu9b"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-d63a650ac783cd8ead8a66992a9bc2ee",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "8979f704-3298-4272-924f-d728353dba05"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "30by0u19f1ehkiw8o76yck5u6"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-d63a650ac783cd8ead8a66992a9bc2ee",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "8979f704-3298-4272-924f-d728353dba05"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "90o04w0xh3pwe1oz5tdi0kf54"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false"
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/26/2012 18:00"
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAAA/AAEADEFHTk9TVElDLkNPTQAMY2xvdWRlcmEtc2NtAAAAAVnU+scBABcAEO3a7dpTsfEoUF4xHDgGR7wAAAAB"
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@AGNOSTIC.COM"
    }, {
      "name" : "KDC_HOST",
      "value" : "ip-172-31-13-246.us-west-2.compute.internal"
    }, {
      "name" : "KRB_ENC_TYPES",
      "value" : "arcfour-hmac"
    }, {
      "name" : "KRB_MANAGE_KRB5_CONF",
      "value" : "true"
    }, {
      "name" : "MAX_RENEW_LIFE",
      "value" : "604800"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    }, {
      "name" : "SECURITY_REALM",
      "value" : "AGNOSTIC.COM"
    } ]
  }
}

```