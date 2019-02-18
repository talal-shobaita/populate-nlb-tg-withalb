# populate-nlb-tg-withalb

This lambda function is used to setup AWS ip based target groups with dns names, when you dont control the Ip addresses. It resolves the provided endpoint periodailly and update the target group. This is forked from aws github repo and modified to work with endpoints that resolves to public Ip addresses as well, it will describe network interfaces and map the private Ip addresses to the target group.

source:
https://aws.amazon.com/blogs/networking-and-content-delivery/using-static-ip-addresses-for-application-load-balancers/
