# openstack-first-steps

Started by creating a ubuntu server in AWS account
Followed http://itechgenie.com/myblog/2016/12/installing-openstack-on-aws/ - except that I didn't create a user nor updated local.conf
created stack using ./stack.sh  --> took 12 minutes on a c4.xlarge instance
Modified EC2 instance security group to allow HTTP/80 traffic
Loggged into <IP-address>/dashboard  using 'admin' user
  - try creating an instance, but didn't allow since there is no default network
  - <to explore how to create a network through heat templates>

For running openstack CLI  ( ref: https://docs.openstack.org/heat/latest/getting_started/create_a_stack.html) 
 - sudo pip install  python-openstackclient
 - source openrc  (used default values) 
 - tested with "openstack image list" command -> success
 
To run tempest test 
  - not useful -> http://fosshelp.blogspot.com/2014/02/how-to-manually-install-openstack.html?m=1
  - sudo pip install tempest
  - tempest init cloud-01
  - cd cloud-01 & verofied there is default tempest.sample.conf file in etc folder
  - rename the file to tempest.conf, and 
    - update auth_urls for v2 and v3, and user name and password for 'admin' user
    - clouds.yaml can be downloaded from API section of dashboard which contains pertaining details.
  - tempest run --workspace clould-01   --> failed with auth ..etc errors
    - before running tests make sure increase the volume size to 16 GB.


Reference notes from ./stack.sh output:

This is your host IP address: 172.30.0.160
This is your host IPv6 address: ::1
Horizon is now available at http://172.30.0.160/dashboard
Keystone is serving at http://172.30.0.160/identity/
The default users are: admin and demo
The password: nomoresecret

Services are running under systemd unit files.
For more information see:
https://docs.openstack.org/devstack/latest/systemd.html

DevStack Version: pike
Change: dea3083d984569eac9647f1a28f10ae98afc42f7 Fix path to mlock_report 2017-08-01 08:15:07 +0300
OS Version: Ubuntu 16.04 xenial
