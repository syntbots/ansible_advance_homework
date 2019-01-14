## Provision QA Environment
1.	SSH to Bastion 
2.	Copy opentlc user account private  key file to Bastion
3.	Verify the SSH connectivity to workstation machine using opentlc user account
4.	clone https://github.com/syntbots/ansible_advance_homework.git  to bastion root
5.	Set the Environment Variables
```
export OSP_GUID=xxxx
```
6.  Execute site-setup-workstation.yml
      *  Public network named ext_network will be created
      *  Private network named int_network will be created
      *  Security group to allow services running in RHOSP  instances accessible from workstation
      *	 Custom hardware profile for creating RHOSP instances
      *  Key pair named ansible_ssh for attaching to RHOSP instances
      *	 Custom image named rhel_image will be created to provision RHOSP instances
      *	 SSH connectivity using cloud-user account between bastion and workstation using openstack keys files
      *	 Setup workstation as isolation node ; instance group osp will be created
  7.	Execute site-osp-instances.yml play book which invokes osp-servers  role to provision RHOSP instances
  8.	Site-3tier-app.yml will install services as follows
      *	Haproxy in frontend 
      *	Tomcat in app1 and app2
      *	Postgres in appdb1
  9.	Execute site-smoke-osp.yml playbook to run smoke test on QA environment
  10.	If QA setup is done properly smoke test will be success.



## Provision PROD Environment



## Design Ansible Tower Workflow



