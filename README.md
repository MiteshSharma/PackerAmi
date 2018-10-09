# Packer : Machine Image as a code

Hashicorp Packer is a lightweight, easy to use tool which automates the creation of any type of machine images for multiple platforms. Packer is not a replacement of configuration management tools like Ansible. Packer works with tools like ansible to install software while creating images. Packer uses a configuration file to create a machine image. Packer uses the concepts of builders to spin up an instance, run provisioners to configure applications or services. Once setup is done, it shutdown instance and save new baked machine instance with any needed post-processing. Packer only builds images. We need to manage them by yourself.

Packer configuration file has three main components:

1. User variable: User variables are used to parameterized packer configuration file template so we can keep secret, environment variables and other parameters out of the template. They help with the portability of configuration file. They help to separate out the part which can be modified in our template. Variables can be passed through command lines, environment variables, Vault or files. The variable section is a key value mapping with the variable name assigned to a default value. 

2. Builder: Builders section contains a list of builders that packer uses to generate a machine image. Builders are responsible for creating an instance and generating machine images from them. A builder maps to a single machine image. Builder contains information including type which is the name of the builder, access keys which builder require to connect to the platform like AWS. 

3. Provisioners: Provisioners section contains a list of provisioners that packer uses to install and configure software within running instance before creating a machine image. Provisioners are optional. Provisioner contains type which specifies the name of provisioner like Shell, Ansible etc.


Setup:

Step 1: Install packer from here : https://packer.io/downloads.html

Step 2: Setup AWS_ACCESS_KEY environment variable with AWS access key

Step 3: Setup AWS_SECRET_ACCESS_KEY environment variable with AWS secret key

Step 4: Run packer command to build : "packer build example.json"
