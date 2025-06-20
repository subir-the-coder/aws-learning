# AWS IAM Notes

**Status:** In Progress

#### All about IAM Users, Groups and Policies

#### Keypoints:

IAM is global, so this service is found in every region
**TIP:** Never use root account
A user can be a member of nultiple groups or no groups.
Policies can be attached to groups/users, through which users inherits
Groups cannot contain another group

We create users and groups, to allow/deny services, through JSON documents known as Policies, in AWS Least Privilege Principals is applied. Policies are attached to groups or users.

JSON document contains 
- Version
- Statements
  - SID
  - Effect (allow/deny)
  - Action (What action needds to be done)
  - Resource (On which services)
  - Condition

Example:

<pre>{
  "Version" : "2012-10-17",
  "Statement" : [
    {
      "Effect" : "Allow";
      "Action" : "ec2:Describe",
      "Resource" : "*"
    }
  ]
}</pre>



