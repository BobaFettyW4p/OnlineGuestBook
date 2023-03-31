Online Guest Book
=================

.. image:: https://user-images.githubusercontent.com/111187499/218286042-91e5698e-e269-4dbb-b5b1-4999cc452d6e.png

To see an example of this project in action, click `here <http://guestbook.mivancic.com>`_

NOTE: As of 3/30/22, this project is no longer using this infrastructure and has been migrated to a serverless version as hosted `here <https://github.com/BobaFettyW4p/GuestbookEnhanced>`_

This repo contains all of the terraform configuration files needed to create a web server infrastructure on AWS to host
a simple 'Online Guestbook' webapp:

#. An `EC2 Instance <https://github.com/BobaFettyW4p/OnlineGuestbookTerraform/blob/main/ec2.tf>`_ that will act as our web server
#. A `Virtual Private Cloud (VPC) <https://github.com/BobaFettyW4p/OnlineGuestbookTerraform/blob/main/vpc.tf>`_ for our web server to reside in
#. A `subnet <https://github.com/BobaFettyW4p/OnlineGuestbookTerraform/blob/main/subnet.tf>`_ to handle addressing within the VPC
#. A `routing table <https://github.com/BobaFettyW4p/OnlineGuestbookTerraform/blob/main/routeTable.tf>`_ to handle routing between the VPC and the wider internet
#. A `security group <https://github.com/BobaFettyW4p/OnlineGuestbookTerraform/blob/main/securityGroup.tf>`_ to authorize traffic routing to and from the VPC
#. All of which interface with `Route53 <https://github.com/BobaFettyW4p/OnlineGuestbookTerraform/blob/main/route53.tf>`_ to utilize the desired domain for name resolution/routing  

All non-Route53 resources created as a result of this project are Free Tier-eligible (Route53 should cost ~$1.00 a month to operate, barring large amounts of traffic)

Pre-requisites
--------------
#. AWS account with Power User privileges
#. A pre-existing key pair. For info on creating one, please refer to `this documentation from AWS <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-key-pairs.html>`_
#. terraform locally installed
#. domain hosted via Route53 or any other DNS service

Usage
-----
1. Update the domain_name and instance_key variable in `terraform.tfvars <https://github.com/BobaFettyW4p/OnlineGuestbookTerraform/blob/main/terraform.tfvars>`_ with your desired values (if Route53 DNS services are not desired, simply delete `route53.tf <https://github.com/BobaFettyW4p/OnlineGuestbook/blob/main/route53.tf>`_)
2. Ensure your AWS credentials are properly passed to your terminal session
3. Apply the terraform configuration:


.. code-block:: bash


      terraform init
   
      terraform apply


NOTE: As part of the installation, your EC2 instance will utilize the files from the `sister repository <https://github.com/BobaFettyW4p/OnlineGuestBookConfig>`_ to configure the web server/app.

4. Once complete, terraform will return the public IP address of your EC2 instance as the value of the `web_instance_ip` variable

post install, you may need to delegate DNS authority to the newly-created hosted zone. For more information, please refer to my `blog post <https://blog.mivancic.com/route53-hosted-zone-delegation>`_ on how to do this
