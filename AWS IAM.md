# AWS IAM Notes

**Status:** Complete

#### All about IAM Users, Groups and Policies

#### Keypoints:

- IAM is global, so this service is found in every region
- **TIP:** Never use root account
- A user can be a member of nultiple groups or no groups.
- Policies can be attached to groups/users, through which users inherits and also roles
- Groups cannot contain another group

We create users and groups, to allow/deny services, through JSON documents known as Policies, in AWS Least Privilege Principals is applied. Policies are attached to groups or users.

#### IAM Roles are for temporary access, often assumed by services or external identities. IAM Users are permanent identities for people or services.

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


## IAM Authentication

**IAM Password policy** can be set for user accounts
- minimum password length
- require specific characters
- password expiration
- change password at user login
- prevent password reuse

#### MFA (Multi Factor Authentication) MFA = Password + Security Device generating a token

- Virtual Authentication Device (Google Authenticator, Authy)
- Universal 2nd Factor (U2F) this is a physical device like a YubiKey
- Hardware Key Fob (MFA Device) provided by Gemalto
- Hardware Key Fob (MFA Device) for AWS Gov Cloud, provided by Surepass ID

To setup, in root, go to accounts and Add MFA

#### Accessing AWS
- Web Interface (Web Management Console) Protected by Password + MFA
- AWS CLI, protected by Access Keys
- AWS SDK (Software Development Kit), Code: protected by access keys

Access Keys are generated from management console
Users are responsible for their own access keys

Only 2 active access keys are allowed, lost access keys cannot be retrieved.

aws configure

In case old access key is forgot, create a new one, and delete the old one.

#### IAM Roles

Some AWS service needs to perform actions on our behalf, and to do so, we assign permission to AWS Services with IAM Roles.

#### IAM Security Tools

- IAM Credential Report (account-level)
  - A report that lists all accounts users and status of their various credentials

- IAM Access Advisor
  - Service permissions granted to a user and when those services were last accessed.







