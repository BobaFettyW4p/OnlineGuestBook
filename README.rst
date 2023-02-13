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
#. Update the domain_name and instance_key variable in `terraform.tfvars <https://github.com/BobaFettyW4p/OnlineGuestbookTerraform/blob/main/terraform.tfvars>`_

#. Run the below commands
.. code-block:: bash

   terraform init
   terraform apply


post install, you may need to delegate DNS authority to the hosted zone created for the domain set in terraform.tfvars. For more information, please refer to my `blog post <https://blog.mivancic.com/route53-hosted-zone-delegation>`_ on this
