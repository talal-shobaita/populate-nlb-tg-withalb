# populate-nlb-tg-withalb

This lambda function is used to setup AWS ip based target groups with dns names, when you dont control the Ip addresses. It resolves the provided endpoint periodailly and update the target group. This is forked from aws github repo and modified to work with endpoints that resolves to public Ip addresses as well, it will describe network interfaces and map the private Ip addresses to the target group.


Configurable environment variables:

ALB_DNS_NAME – the full DNS name (FQDN) of the ALB
ALB_LISTENER – The traffic listener port of the ALB
S3_BUCKET – Bucket to track changes between Lambda invocations
NLB_TG_ARN – The ARN of the NLBs target group
MAX_LOOKUP_PER_INVOCATION – The max times of DNS look per invocation. The default value is 50 in the CloudFormation template.
INVOCATIONS_BEFORE_DEREGISTRATION – Then number of required Invocations before an IP address is deregistered. The default value is 3 in the CloudFormation template.
CW_METRIC_FLAG_IP_COUNT – The controller flag that enables the CloudWatch metric of the IP address count. The default value is “true” in the CloudFormation template.


source:
https://aws.amazon.com/blogs/networking-and-content-delivery/using-static-ip-addresses-for-application-load-balancers/
