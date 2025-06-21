# AWS IAM Notes

**Status:** In Progress

#### All about IAM Users, Groups and Policies

#### Keypoints:

- IAM is global, so this service is found in every region
- **TIP:** Never use root account
- A user can be a member of nultiple groups or no groups.
- Policies can be attached to groups/users, through which users inherits
- Groups cannot contain another group

We create users and groups, to allow/deny services, through JSON documents known as Policies, in AWS Least Privilege Principals is applied. Policies are attached to groups or users.

JSON document contains 
- Version
- id
- Statements
  - SID (optional)
  - Principal - (which account/user/role the policy to be applied)
  - Effect (allow/deny)
  - Action (What action needds to be done, i.e the list of API calls)
  - Resource (On which services, list of resources)
  - Condition (when the policy is to be applied, optional)

Example of a policy:

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

Policies are attached to Groups, and are inherited by users.
**Note:** Policies can directly also be attached to users but is not a good practise.

Own policies can be created too, from IAM >> Policies
We have a Visual Editor and a JSON Editor to create a custom policy

#### So learnt how to attach Policies to a user, through Groups and directly. Also learnt how to create custom Policy

🔐 IAM Evaluation Logic
AWS IAM uses additive permissions:

All attached policies (user policies, group policies, managed or inline) are combined.

If any of them allows an action, and none explicitly deny, the action is allowed.

#### In case:

Custom policy only allows ListUsers and GetUser.

But AdministratorAccess via the group allows everything, including iam:CreateUser.

So IAM evaluates the union of both policies. Since nothing explicitly denies iam:CreateUser, and AdministratorAccess allows it

**TIP:** An explicit Deny always wins, even if another policy allows it.


