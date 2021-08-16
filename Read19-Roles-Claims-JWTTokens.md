# Reading Notes 19 - Roles, Claims and JWT Tokens

## Claims-based Authorization
When an identity is created it may be assigned one or more claims issued by a trusted party. A claim is a name value pair that represents what the subject is, not what the subject can do.  

For example, 
You may have a driver's license, issued by a local driving license authority. Your driver's license has your date of birth on it. In this case the claim name would be DateOfBirth, the claim value would be your date of birth, for example 8th June 1970 and the issuer would be the driving license authority. The door security officer would evaluate the value of your date of birth claim and whether they trust the issuer (the driving license authority) before granting you access. Think of claims as "properties" that a role has.

## Claims based authorization, at its simplest, checks the value of a claim and allows access to a resource based upon that value.

## An identity can contain multiple claims with multiple values and can contain multiple claims of the same type.





