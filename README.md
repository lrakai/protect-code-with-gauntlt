# protect-code-with-gauntlt

Demonstration of how Gauntlt can protect your code from well-known attacks

![Final Environment](https://user-images.githubusercontent.com/3911650/38643036-2306a980-3d99-11e8-82e0-68b61acf61b0.png)

## Getting Started

Deploy the CloudFormation `infrastructure/cloudformation.json` template. The template creates a user with the following credentials and minimal required permisisons to complete the Lab:

- Username: _student_
- Password: _password_

## Instructions

- Add a Test stage in between the source and build stage in CodePipeline
  - The Test stage should use the App-Test CodeBuild projectc created by the CloudFormation template
  - The stage should use the SourceOutput as its input artifact
- Open the Cloud9 IDE created by CloudFormation
- Create the buildspec.yml and buildspec.test.yml files included in the `src/cicd/` directory in the Cloud9 environment
- zip the the two YAML files into a file called src.zip
- Upload src.zip to the S3 bucket with `codeartifacts` in its name
- Watch the CodePipeline process the new source and eventually fail on the Test stage
- Open the CodeBuild error to inspect the Gauntlt report for which attack failed

## Cleaning Up

Delete the CloudFormation stack to remove all the resources used in the Lab.