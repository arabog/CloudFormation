# CloudFormation
Creating an S3 bucket with AWS CloudFormation.

## Steps:
*1. Create CloudFormation Stack*  
Navigate to CloudFormation page
![form1](form1.png?raw=true "form1")

Select Designer from the left-hand menu.  
Locate S3 in the Resource Type section and expand it.  
Select Bucket and drag it to the designer window on the right-hand side. It comes with this:    
{
    "Resources": {
        "S3BRX59": {
            "Type": "AWS::S3::Bucket",
            "Properties": {}
        }
    }
}`
`
Copy the JSON below and replace entirely the JSON found in the Properties tab  

{
    "AWSTemplateFormatVersion": "2010-09-09",
    "Description": "Basic S3 Bucket CloudFormation template",
    "Resources": {
        "S3BucketCreatedByCloudFormation": {
            "Type": "AWS::S3::Bucket",
            "DeletionPolicy": "Delete",
            "Properties": {
                "AccessControl": "PublicRead"
            }
        }
    },

    "Outputs": {
        "BucketName": {
            "Value": {
                "Ref": "S3BucketCreatedByCloudFormation"
            },
            "Description": "Name of the newly created Amazon S3 Bucket"
        }
    }
}

Hit the Refresh button in the upper right-hand corner so that the Designer is not out of date  

![form2](form2.png?raw=true "form2")

*2. Save CloudFormation Stack*  
In the CloudFormation Designer Toolbar, click the Document icon , and click Save.  
Click Local File and click Save. The JSON file will download.  
In the AWS CloudFormation Designer toolbar, click to validate your template. You will see a message that states, Template is valid.  

![form3](form3.png?raw=true "form3")

*3. Deploy CloudFormation Stack*  
In the CloudFormation Designer Toolbar, click to deploy the stack. The Create stack screen appears.  
Accept the defaults and click Next.  
Enter a Stack name. Leave Parameters empty. Click Next.  
Leave the defaults and click Next.  
Review the stack details and click Create Stack. The stack status will be CREATE_IN_PROGRESS. To the current status of the stack, select the Refresh button in the upper right-hand corner. Once the stack reaches the CREATE_COMPLETE status, the stack has been deployed.  

![form4](form4.png?raw=true "form4")

![form5](form5.png?raw=true "form5")

*4. View S3 Bucket created by CloudFormation Stack*  
![form6](form6.png?raw=true "form6")

*5. Delete CloudFormation Stack*

