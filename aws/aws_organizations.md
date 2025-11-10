# AWS Organizations

[User Guide AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_introduction.html)

## What is AWS Organizations?

Centrally manage your environment as you scale your AWS resources

AWS Organizations helps you centrally manage and govern your environment as you grow and scale your AWS resources. Using Organizations, you can create accounts and allocate resources, group accounts to organize your workflows, apply policies for governance, and simplify billing by using a single payment method for all of your accounts.

Organizations is integrated with other AWS services so you can define central configurations, security mechanisms, audit requirements, and resource sharing across accounts in your organization. For more information, see Using AWS Organizations with other AWS services.

The following diagram shows a high-level explanation of how you can use AWS Organizations:

* Add accounts
* Group accounts
* Apply policies
* Enable AWS services

<img width="1286" height="282" alt="aws_organization_use" src="https://github.com/user-attachments/assets/f84b1ad2-8c65-4fd8-8e32-3fb3e3bf4e2e" />

## Features for AWS Organizations

AWS Organizations offers the following features:

**Manage your AWS accounts**

AWS accounts are natural boundaries for permission, security, costs, and workloads. Using a multi-account environment is a recommended best-practice when scaling your cloud environment. You can simplify account creation by programmatically creating new accounts using the AWS Command Line Interface (AWS CLI), SDKs, or APIs, and centrally provision recommended resources and permissions to those accounts with AWS CloudFormation StackSets.

**Define and manage your organization**

As you create new accounts, you can group them into organizational units (OUs), or groups of accounts that serve a single application or service. Apply tag polices to classify or track resources in your organization, and provide attribute-based access control for users or applications. In addition, you can delegate responsibility for supported AWS services to accounts so users can manage them on behalf of your organization.

**Secure and monitor your accounts**

You can centrally provide tools and access for your security team to manage security needs on behalf of the organization. For example, you can provide read-only security access across accounts, detect and mitigate threats with Amazon GuardDuty, review unintended access to resources with IAM Access Analyzer, and secure sensitive data with Amazon Macie.

**Control access and permissions**

Set up AWS IAM Identity Center to provide access to AWS accounts and resources using your active directory, and customize permissions based on separate job roles. You can also apply organization policies to users, accounts, or OUs. For example, service control policies (SCPs) enable you to to control access to AWS resources, services, and Regions within your organization. Resource control policies (RCPs) enable you to centrally prevent the unintended use of your AWS resources. Chat applications policies enable you to control access to your organization's accounts from chat applications such as Slack and Microsoft Teams.

**Share resources across accounts**

You can share AWS resources within your organization using AWS Resource Access Manager (AWS RAM). For example, you can create your Amazon Virtual Private Cloud (Amazon VPC) subnets once and share them across your organization. You can also centrally agree to software licenses with AWS License Manager, and share a catalog of IT services and custom products across accounts with AWS Service Catalog.

**Audit your environment for compliance**

You can activate AWS CloudTrail across accounts, which creates a log of all activity in your cloud environment that cannot be turned off or modified by member accounts. In addition, you can set policies to enforce backups on your specified cadence with AWS Backup, or define recommended configuration settings for resources across accounts and AWS Regions with AWS Config.

**Centrally manage billing and costs**

Organizations provides you with a single consolidated bill. In addition, you can view usage from resources across accounts and track costs using AWS Cost Explorer, and optimize your usage of compute resources using AWS Compute Optimizer.
