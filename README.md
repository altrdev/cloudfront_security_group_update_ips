## Cloudfront whitelist lambda
You must create in your infrastructure a security group with specific tags
```
Parameters:
  Protocol:
    Type: String
    AllowedValues:
      - "http"
      - "https"

CloudfrontSecurityGroupGlobal:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupName: cloudfront_ips_whitelist_g
      GroupDescription: Cloudfront IPs whitelist
      Tags:
        - Key: Name
          Value: "cloudfront_g"
        - Key: AutoUpdate
          Value: "true"
        - Key: Protocol
          Value: !Ref Protocol

  CloudfrontSecurityGroupRegional:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupName: "cloudfront_ips_whitelist_r"
      GroupDescription: "Cloudfront IPs whitelist"
      Tags:
        - Key: Name
          Value: "cloudfront_r"
        - Key: AutoUpdate
          Value: "true"
        - Key: Protocol
          Value: !Ref Protocol`
 ```