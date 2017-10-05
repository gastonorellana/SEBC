```

1) What is ubertask optimization?

Es una propiedad dentro de la configuracion de YARN que ejecuta trabajos "suficientemente pequeños" secuencialmente dentro de una sola JVM.

Where in CM is the Kerberos Security Realm value displayed?
2) Administracion -> Seguridad -> 
Pestaña Credenciales Kerberos -> Configuracion : Valor "default_realm"

3) Which CDH service(s) host a property for enabling Kerberos authentication?
 HDFS - YARN - ZOOKEEPER

4) How do you upgrade the CM agents?
 *Se debe tener acceso a internet o generar un repositorio local

a) Log in to the Cloudera Manager Admin Console.
b) Upgrade hosts using one of the following methods:
	- Cloudera Manager installs Agent software
		1- Select Yes, I would like to upgrade the Cloudera Manager Agent packages now and click Continue.
		2- Select the release of the Cloudera Manager Agent to install. Normally, this is the Matched Release for this Cloudera Manager Server. However, if you used a custom repository (instead of archive.cloudera.com) for the Cloudera Manager server, select Custom Repository and provide the required information. The custom repository allows you to use an alternative location, but that location must contain the matched Agent version.
		3- Click Continue. The JDK Installation Options page displays.
			* Leave Install Oracle Java SE Development Kit (JDK) checked to allow Cloudera Manager to install the JDK on each cluster host, or uncheck if you plan to install it yourself.
			* If local laws permit you to deploy unlimited strength encryption, and you are running a secure cluster, check the Install Java Unlimited Strength Encryption Policy Files checkbox.
		 Click Continue.
		4) Specify credentials and initiate Agent installation:
			* Select root or enter the username for an account that has password-less sudo permission.
			* Select an authentication method:
				- If you choose password authentication, enter and confirm the password.
				- If you choose public-key authentication, provide a passphrase and path to the required key files.
			* You can specify an alternate SSH port. The default value is 22.
			* You can specify the maximum number of host installations to run at once. The default value is 10.
		5) Click Continue. The Cloudera Manager Agent packages and optionally the JDK are installed.
		6) Click Continue. The Host Inspector runs to inspect your managed hosts for correct versions and configurations. If there are problems, you can make changes and then rerun the inspector. When you are satisfied with the inspection results, click Continue.

c) Click Finish
d) If you are upgrading from Cloudera Manager 5.0 and are using an external database for Cloudera Navigator, the Database Setup page displays. Configure database settings:
	* Enter the database host, database type, database name, username, and password for the database that you created when you set up the database.
	* Click Test Connection to confirm that Cloudera Manager can communicate with the database using the information you have supplied. If the test succeeds in all cases, click Continue; otherwise check and correct the information you have provided for the database and then try the test again. (For some servers, if you are using the embedded database, you will see a message saying the database will be created at a later step in the installation process.)
e) The Review Changes page displays. Review the configuration changes to be applied and click Continue. The Upgrade wizard displays a dialog box allowing you to choose whether to restart the Cloudera Management Service.
f) Click Continue. If you kept the default selection, the Upgrade wizard restarts the Cloudera Management Service.
g) Click Finish. The Home > Status tab displays.

All services (except for the services you stopped in Stop Selected Services and Roles) should be running.		
  
5) Give the tsquery statement used to chart Hue's CPU utilization?

select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName="hue"

6)Name all the roles that make up the Hive service:

Gateway
Hive Metastore Server
HiveServer2

What steps must be completed before integrating Cloudera Manager with Kerberos?


Step 1:
To install packages for a Kerberos server:

# yum -y install krb5-server krb5-libs krb5-auth-dialog krb5-workstation
To install packages for a Kerberos client:

# yum -y install krb5-workstation krb5-libs krb5-auth-dialog
Step 2:
Server:
–> Change Realm Name > PUNEETHA.COM
–> Add parameters > max_life = 1d and max_renewable_life = 7d

# vim /var/kerberos/krb5kdc/kdc.conf
[kdcdefaults]
 kdc_ports = 88
 kdc_tcp_ports = 88

[realms]
  PUNEETHA.COM = {
  #master_key_type = aes256-cts
  acl_file = /var/kerberos/krb5kdc/kadm5.acl
  dict_file = /usr/share/dict/words
  admin_keytab = /var/kerberos/krb5kdc/kadm5.keytab
  supported_enctypes = aes256-cts:normal aes128-cts:normal des3-hmac-sha1:normal arcfour-hmac:normal des-hmac-sha1:normal des-cbc-md5:normal des-cbc-crc:normal
  max_life = 1d
  max_renewable_life = 7d
 }
Step 3:
Add below properties in All Clients:
> udp_preference_limit = 1
> default_tgs_enctypes = arcfour-hmac
> default_tkt_enctypes = arcfour-hmac

# vim /etc/krb5.conf 
[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = PUNEETHA.COM
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 udp_preference_limit = 1
 default_tgs_enctypes = arcfour-hmac
 default_tkt_enctypes = arcfour-hmac 

[realms] 
  PUNEETHA.COM = {
  kdc = host1.example.com
  admin_server = host1.example.com
 }

[domain_realm]
   .example.com = PUNEETHA.COM
   example.com = PUNEETHA.COM
Step 4:
Create the database using the kdb5_util utility. (Server)

# /usr/sbin/kdb5_util create -s
Loading random data
Initializing database '/var/kerberos/krb5kdc/principal' for realm 'PUNEETHA.COM',
master key name 'K/M@PUNEETHA.COM'
You will be prompted for the database Master Password.
It is important that you NOT FORGET this password.
Enter KDC database master key:
Re-enter KDC database master key to verify:
Step 5:
In Server, add cloudera-scm principal, it will be used by Cloudera Manager later to manage Hadoop principals.

# kadmin.local
kadmin.local:  addprinc cloudera-scm@PUNEETHA.COM
WARNING: no policy specified for cloudera-scm@PUNEETHA.COM; defaulting to no policy
Enter password for principal "cloudera-scm@PUNEETHA.COM":
Re-enter password for principal "cloudera-scm@PUNEETHA.COM":
Principal "cloudera-scm@PUNEETHA.COM" created.
Step 6:
Add */admin and cloudera-scm to ACL(Access Control List), which gives privilege to add principals for admin and cloudera-scm principal

# vim /var/kerberos/krb5kdc/kadm5.acl 
*/admin@PUNEETHA.COM *
cloudera-scm@PUNEETHA.COM admilc
Step 7:
Adds the password policy to the database.

# kadmin.local
kadmin.local:  addpol admin
kadmin.local:  addpol users
kadmin.local:  addpol hosts
kadmin.local:  exit
Step 8:
Start Kerberos using the following commands:

#service krb5kdc start
#service kadmin start

```