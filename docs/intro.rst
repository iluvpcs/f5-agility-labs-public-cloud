Getting Started
---------------

Your instructor will provide you a URL where you can access your Windows  jumphost.

.. NOTE::
	 All work for this lab will be performed exclusively from the Windows
	 jumphost. No installation or interaction with your local system is
	 required.

Lab Topology
~~~~~~~~~~~~

Before you start the lab you will have an empty environment.  You will be building out the following topology.

Network Topology
^^^^^^^^^^^^^^^^^

.. image:: /_static/f5-public-cloud-network-toplogy.png
  :scale: 50%

The following components will be built in your lab environment:

FOR AWS:

- 1-2 x F5-BIG VE WAF (v12.1.2) - Auto Scale WAF
- 2 x F5 BIG-IP VE (v13.0) - Active/Standby cross-AZ deployment
- 2 x Linux Webserver (Amazon Linux AMI)

FOR Azure:

- 1-2 x F5-BIG VE WAF (v12.1.2) - Auto Scale WAF
- 2 x F5 BIG-IP VE (v13.0) - Active/Standby
- 2 x IIS Webservers (Microsoft IIS Image)


Automation Tools
~~~~~~~~~~~~~~~~

During the lab you will be using multiple automation tools.

Without these automation tools you would be required to perform many tasks in precise sequence.

.. image:: /_static/no-automation.png
  :scale: 25%

Using Automation we can simplify this proces to create a faster, safer, and more secure solution.

.. image:: /_static/automation-pipeline.png
  :scale: 25%

By chaining together multiple declarative interfaces and tools.

.. image:: /_static/declarative-interfaces.png
  :scale: 25%


HashiCorp Terraform
^^^^^^^^^^^^^^^^^^^

HashiCorp Terraform is used to create the underlying Network environment, deploy the Linux Webservers, and deploy F5 BIG-IP via AWS Cloud Formation Templates.

Amazon Cloud Formation Templates
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Amazon Cloud Formation Templates (CFT) are used to deploy F5 BIG-IP resources.  In addition to deploying the F5 BIG-IP VE, the CFT template also manages Elastic Network Interfaces (ENI), Security Groups, EC2 Instance Roles, and other cloud native services.

F5 Provides Supported Cloud Formation Templates that customers can leverage in their AWS environments.  The lab will deploy two of these solutions.

#. Auto Scale WAF
#. Active/Standby Pair Across two AWS Availability Zones (AZ)


Azure Azure Resource Manager Templates
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Azure Azure Resource Manager Templates are used to deploy F5 BIG-IP resources.  In addition to deploying the F5 BIG-IP VE, the ARM template also manages  Network Interfaces , Security Groups,  Instance Roles, and other cloud native services.

F5 Provides Azure Azure Resource Manager Templates that customers can leverage in their Azure environments.  The lab will deploy two of these solutions.

#. Auto Scale WAF
#. Active/Standby Pair Across two Azure Availability Zones (AZ)



F5 Super NetOps Container
^^^^^^^^^^^^^^^^^^^^^^^^^^

To simplify the installation of these Automation Tools (Terraform/CFT) we will use the F5 Super NetOps Container to provide a consistent environment for running the labs.

Connecting to the Lab Environment
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Why do we use Ravello Portal?  We want a simple single jump point to do our labs, and having a windows JumpBox allows us to control that environment so it is identical for every student.
Yes you can run these docker images directly on your computer and skip our Ravello Jumpbox starting point, but we find some students have locked down workstations and might struggle to get docker installed, for this reason we use the Ravello RDP Windows Jumpbox to make this lab uniform for all students.

Your instructor will provide directions on how to connect to the Ravello Portal.

Ravello Portal
^^^^^^^^^^^^^^

On the Ravello Portal page click on the RDP link.

.. image:: /_static/rdp-ravello-portal.png

The username / password for the RDP connection will be visible below the link.

Launching Putty
^^^^^^^^^^^^^^^

On the Windows Jumphost Desktop you should see a icon for Putty.

.. image:: /_static/putty-link.png

Double click on it.  Click on "docker" then "Load" followed by "Open".

.. TIP::
   Ignore any SSH key errors that you see.

.. image:: /_static/putty-load.png
  :scale: 50%

You should see a Putty window.

.. image:: /_static/putty-window.png
  :scale: 50%

You are now ready to proceed with the lab.
