# CNAME to CloudFront

I summarized contents more simply with the custom domain.

1. Configure the DNS service for the domain to route traffic for the domain in `CNAME`.
2. Sign in to the AWS Management Console and open the CloudFront console at https://console.aws.amazon.com/cloudfront/.
3. Choose the `ID` for the distribution that you want to update.
4. On the **General** tab, choose `Edit`.
5. Update the `Alternate Domain Names (CNAMEs)`
6. Choose `Yes, Edit`.
Confirm that Distribution Status has changed to Deployed.

[Reference](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/CNAMEs.html)
