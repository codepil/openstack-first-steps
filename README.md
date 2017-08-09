# openstack-first-steps

Started by creating a ubuntu server in AWS account
Followed http://itechgenie.com/myblog/2016/12/installing-openstack-on-aws/ - except that I didn't create a user nor updated local.conf
created stack using ./stack.sh  --> took 10 min on a c4.xlarge instance
Modified EC2 instance security group to allow HTTP/80 traffic
Loggged into <IP-address>/  using 'admin' user
  - try creating an instance, but didn't allow since there is no default network
  - <to explore how to create a network through heat templates>

For running openstack CLI  ( ref: https://docs.openstack.org/heat/latest/getting_started/create_a_stack.html) 
 - sudo pip install  python-openstackclient
 - source openrc  (used default values) 
 - tested with "openstack image list" command
 
To run tempest test ( ref: 
 - 
