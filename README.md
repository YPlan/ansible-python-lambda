ansible-python-lambda
=====================

An example of deploying [AWS Lambda][lambda] functions with [Ansible][ansible],
for our blog post titled rather obviously [“Deploying Amazon Lambda Functions
with Ansible.”][blogpost]

Requirements
------------

To run this, you will need:

* Python and a recent `pip`
* Ansible 2.0+ (`pip install ansible`)
* Boto, configured to work on your target AWS account (`pip install boto`)
* The AWS CLI (`pip install awscli`)

Usage
-----

1. Make a new S3 bucket in your default boto region with versioning on, and
   update `playbook.yml` so the `s3_bucket` var has the correct bucket name,
   and `aws_region` with the region it is in, which is where the Lambda etc.
   will be created too.

2. Run `ansible-playbook playbook.yml`. It will create a Cloudformation stack
   in your AWS account called `my-lambda-function` that runs the example Lambda
   function every day at 08:00 UTC, logging "Hello World".

3. Play with it and use the code to get your own Lambda functions running!

[lambda]: https://aws.amazon.com/lambda/
[ansible]: https://www.ansible.com/
[blogpost]: https://tech.yplanapp.com/2016/05/27/deploying-amazon-lambda-functions-with-ansible/
