# cloudform_templates

This repository is where we will maintain templates for Amazon Cloudform resource creation. 

The folder structure follows the patterns outlined by sceptre (https://github.com/cloudreach/sceptre) allowing for:

* Manual usage via template upload
* Semi-automated command line usage via sceptre

You will need to install Amazon CLI to use the templates with Sceptre. In addition you will need python and a _virtualenv_. 
Instructions for both are linked in the sceptre installation guide (https://sceptre.cloudreach.com/latest/docs/install.html)

Usage:
* Under the root **config** folder, create any number of "environments"
    * add a _config.yaml_ with any configuration universal to that environment (IAM_role, region, etc)
    * add a yaml file for each resource you with to create containing any resource specific parameters and a _template_path_
* Under the root **templates** folder, create your Cloudform templates corresponding to the previously created configuration files
    * templates can be JSON, YAML, or .template format
    * make sure to define all parameters at the beginning of the template
    * insert parameter values using the _Ref_ structure
* To create a new stack _**sceptre create-stack** [environment] [resource]_
    * Other sceptre options are available here:  https://sceptre.cloudreach.com/latest/docs/cli.html
    