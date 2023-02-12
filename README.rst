Online Guest Book
=================

.. image:: https://user-images.githubusercontent.com/111187499/218286042-91e5698e-e269-4dbb-b5b1-4999cc452d6e.png

Pre-requisites
--------------
#. AWS account with Power User privileges
#. A pre-existing key pair. For info on creating one, please refer to `this documentation from AWS <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-key-pairs.html>`_
#. terraform locally installed
#. custom domain (hosted via Route53 or any other DNS service)

Installation
------------
1. update the domain_name and instance_key variable in `terraform.tfvars <https://github.com/BobaFettyW4p/OnlineGuestbookTerraform/blob/main/terraform.tfvars>`_ to reflect your custom domain/desired top-level domain with your values

.. code-block:: bash

   terraform init
   terraform apply
   
post install, you will need to 
