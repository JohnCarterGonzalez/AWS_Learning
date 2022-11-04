IAM 
  - Identity and Access Management 
    root account created by default, dont use it 
  - Users are people within your organization, can be grouped 
    -> Groups only contain users, no nested Groups
    -> can be liberal with users in groups but use least privilege possible 
    -> Users or groups can be assigend JSON dox called policies 

  - IAM Policy Inheritance
    -> if a user has crossover with more than one group, AWS takes least privilege 
        stance 
    -> IAM policy Structure 
      Version policy, an ID, and a statment
      Statement consists of: 
        => Sid, an identifer for the statement 
        => Effect, whether the statement allows or denies Access
        => Principle, account/user/role to which this policy applies 
        => Action list of actions this policy allows or denies 
        => Condition, conditions for when this policy is in effect
        => Effect, Principle, Action, Resource, IMPORTANT for EXAM
