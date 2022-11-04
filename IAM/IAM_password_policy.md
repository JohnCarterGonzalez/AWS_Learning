IAM password policy
  - strong passwords = higher security 
  - password policies => 
    require specific character types and lengths 
    require users to change their passwords after some time 
    prevent password reuse
    
  MFA 
    - multi factor authentication
      use to protect root account, and IAM users 
      MFA => password you know and a security device the user owns 
      even the password is stolen or hacked, the account is not compromised
    - Options:
      Virtual MFA device
        -> google authenticator => one device 
        -> authy => multi device 
      Universal 2nd factor (u2F) security Key
        -> Yubikey => physical device (like a USB), supports mutiple users 
      Hardware KeyFob MFA device
      Hardware Key Fob MFA Device for AWS GovCloud
  How can users access AWS?
    - AWS management console
    - AWS CLI protected by access keys 
      -> tool that allows you to interact withAWES services using commands in CLI
      -> direct access to the public APIs of AWS services
      -> alternative to management console
    - AWS Software Development Kit - for code 
      -> langauge specific APIS 
      -> embedded within your application

