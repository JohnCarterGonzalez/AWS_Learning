IAM ROles for Services
  - Some AWS service wil need to perfomr actions on our behalf 
  - assign permissions to AWS services w/IAM Roles 
  - Commmon ROles:
    EC@ instance Roles
    lambda function roles 
    roles for cloud 
  IAM Security Tools
    - IAM Credentials Report (account-level)
      lists all your accounts users and the status of theis various Credentials
    - IAM access advisor (user-level)
      access advisor shows the service permissions granted to a user and when those
      services were last used 
      can be used to revise your policies 
  IAM best practices 
    - dont use root acct unless setting up AWS acct 
    - one aws user = one user
    - can assign users to groups and assign permisssions to groups 
    - create a strong password policy 
    - use and enforce MFA 
    - create and use ROles for giving permissions to AWS 
    - use access keys for programmatic access (cli/sdk)
    - audit permissions of your acct w/the IAM credentials Report
    - never share IAM users & access keys 
