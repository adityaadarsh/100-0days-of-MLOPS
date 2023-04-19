

AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. It enables you to manage users, groups, and permissions to access AWS resources. In this blog, we will cover some of the basic tutorials to get started with AWS IAM.

## Tutorial 1: Creating a New User

To create a new user, follow these steps:

1.  Log in to the AWS Management Console.
2.  Navigate to the IAM dashboard.
3.  Click on the "Users" tab.
4.  Click on the "Add User" button.
5.  Enter the user details, including the username and access type.
6.  Create a password for the user.
7.  Click on the "Create User" button.

## Tutorial 2: Creating a New Group

To create a new group, follow these steps:

1.  Log in to the AWS Management Console.
2.  Navigate to the IAM dashboard.
3.  Click on the "Groups" tab.
4.  Click on the "Create New Group" button.
5.  Enter a name for the group.
6.  Select the policies that you want to attach to the group.
7.  Click on the "Create Group" button.

## Tutorial 3: Creating a New Role

To create a new role, follow these steps:

1.  Log in to the AWS Management Console.
2.  Navigate to the IAM dashboard.
3.  Click on the "Roles" tab.
4.  Click on the "Create Role" button.
5.  Select the type of trusted entity for your role.
6.  Attach policies to your role.
7.  Click on the "Create Role" button.

## Tutorial 4: Adding Permissions to a User

To add permissions to a user, follow these steps:

1.  Log in to the AWS Management Console.
2.  Navigate to the IAM dashboard.
3.  Click on the "Users" tab.
4.  Select the user that you want to add permissions to.
5.  Click on the "Add Permissions" button.
6.  Choose the type of permission that you want to add.
7.  Select the resources that you want to grant access to.
8.  Click on the "Add Permissions" button.

## About AWS IAM Policies

![[Pasted image 20230417221436.png]]
IAM policies in AWS are JSON documents that allow you to define permissions for your AWS resources. These policies can be attached to users, groups, or roles to control access to specific resources. An IAM policy is made up of one or more statements, each containing a list of permissions for a specific resource or group of resources. Each statement includes a list of actions, which define the specific operation that can be performed on the specified resources, and a list of resources, which define the resources that the policy applies to.

IAM policies are an awesome way to grant or deny access to AWS resources, and they can be used to create fine-grained access controls for specific resources or groups of resources. They can also be used to grant cross-account access to AWS resources, which lets users from one AWS account access resources in another AWS account.

When setting up an IAM policy, remember to follow the principle of least privilege. That means users should only be given the permissions they need to do their job. This helps to prevent any accidental or intentional misuse of AWS resources.

So, IAM policies are a super important tool for managing access to AWS resources, and they provide an easy and flexible way to control access to specific resources or groups of resources.

## Some Basic questions

**Q. What is the need of IAM?**

A. IAM is needed to securely control access to AWS resources by managing users, groups, and permissions.

**Q. Please define a scenario in which you would like to create your own IAM policy.**

A. An example scenario would be to restrict access to a specific S3 bucket to only a certain group of users in your organization, and to only allow them to perform specific actions, such as read or write access.

**Q. Why do we prefer not using root account?**

A. We prefer not using the root account because it has full access to all AWS resources, and any mistake or compromise can cause significant damage.

**Q. How to revoke policy for an IAM user?**

A. To revoke a policy for an IAM user, you need to navigate to the IAM Dashboard, select the user, and remove the policy from their permissions.

**Q. Can a single IAM user be a part of multiple policies via group and root? how?**

A. Yes, a single IAM user can be a part of multiple policies via group and root. This is achieved by attaching policies to groups, and then adding users to those groups. Root account also has full access to all the policies.