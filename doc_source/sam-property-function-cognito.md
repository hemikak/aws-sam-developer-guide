# Cognito<a name="sam-property-function-cognito"></a>

The object describing an event source with type Cognito\.

## Syntax<a name="sam-property-function-cognito-syntax"></a>

To declare this entity in your AWS SAM template, use the following syntax:

### YAML<a name="sam-property-function-cognito-syntax.yaml"></a>

```
  [Trigger](#sam-function-cognito-trigger): List
  [UserPool](#sam-function-cognito-userpool): String
```

## Properties<a name="sam-property-function-cognito-properties"></a>

 `Trigger`   <a name="sam-function-cognito-trigger"></a>
The Lambda trigger configuration information for the new user pool\.  
*Type*: List  
*Required*: Yes  
*CloudFormation Compatibility*: This property is passed directly to the `[LambdaConfig](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-cognito-userpool-lambdaconfig.html)` property of an `AWS::Cognito::UserPool`\.

 `UserPool`   <a name="sam-function-cognito-userpool"></a>
Reference to UserPool defined in the same template  
*Type*: String  
*Required*: Yes  
*CloudFormation Compatibility*: This property is unique to AWS SAM and does not have an AWS CloudFormation equivalent\.

## Examples<a name="sam-property-function-cognito--examples"></a>

### Cognito Event<a name="sam-property-function-cognito--examples--cognito-event"></a>

Cognito Event Example

#### YAML<a name="sam-property-function-cognito--examples--cognito-event--yaml"></a>

```
CognitoUserPoolPreSignup:
  Type: Cognito
  Properties:
    UserPool:
      Ref: MyCognitoUserPool
    Trigger: PreSignUp
```