Terraform_cloudfront_module
<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.13.1 |
| aws | >= 4.29 |

## Providers

| Name | Version |
|------|---------|
| aws | >= 4.29 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_cloudfront_distribution.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudfront_distribution) | resource |
| [aws_cloudfront_monitoring_subscription.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudfront_monitoring_subscription) | resource |
| [aws_cloudfront_origin_access_control.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudfront_origin_access_control) | resource |
| [aws_cloudfront_origin_access_identity.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudfront_origin_access_identity) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| aliases | Extra CNAMEs (alternate domain names), if any, for this distribution. | `list(string)` | `null` | no |
| comment | Any comments you want to include about the distribution. | `string` | `null` | no |
| create\_distribution | Controls if CloudFront distribution should be created | `bool` | `true` | no |
| create\_monitoring\_subscription | If enabled, the resource for monitoring subscription will created. | `bool` | `false` | no |
| create\_origin\_access\_control | Controls if CloudFront origin access control should be created | `bool` | `false` | no |
| create\_origin\_access\_identity | Controls if CloudFront origin access identity should be created | `bool` | `false` | no |
| custom\_error\_response | One or more custom error response elements | `any` | `{}` | no |
| default\_cache\_behavior | The default cache behavior for this distribution | `any` | `null` | no |
| default\_root\_object | The object that you want CloudFront to return (for example, index.html) when an end user requests the root URL. | `string` | `null` | no |
| enabled | Whether the distribution is enabled to accept end user requests for content. | `bool` | `true` | no |
| geo\_restriction | The restriction configuration for this distribution (geo\_restrictions) | `any` | `{}` | no |
| http\_version | The maximum HTTP version to support on the distribution. Allowed values are http1.1, http2, http2and3, and http3. The default is http2. | `string` | `"http2"` | no |
| is\_ipv6\_enabled | Whether the IPv6 is enabled for the distribution. | `bool` | `null` | no |
| logging\_config | The logging configuration that controls how logs are written to your distribution (maximum one). | `any` | `{}` | no |
| ordered\_cache\_behavior | An ordered list of cache behaviors resource for this distribution. List from top to bottom in order of precedence. The topmost cache behavior will have precedence 0. | `any` | `[]` | no |
| origin | One or more origins for this distribution (multiples allowed). | `any` | `null` | no |
| origin\_access\_control | Map of CloudFront origin access control | ```map(object({ description = string origin_type = string signing_behavior = string signing_protocol = string }))``` | ```{ "s3": { "description": "", "origin_type": "s3", "signing_behavior": "always", "signing_protocol": "sigv4" } }``` | no |
| origin\_access\_identities | Map of CloudFront origin access identities (value as a comment) | `map(string)` | `{}` | no |
| origin\_group | One or more origin\_group for this distribution (multiples allowed). | `any` | `{}` | no |
| price\_class | The price class for this distribution. One of PriceClass\_All, PriceClass\_200, PriceClass\_100 | `string` | `null` | no |
| realtime\_metrics\_subscription\_status | A flag that indicates whether additional CloudWatch metrics are enabled for a given CloudFront distribution. Valid values are `Enabled` and `Disabled`. | `string` | `"Enabled"` | no |
| retain\_on\_delete | Disables the distribution instead of deleting it when destroying the resource through Terraform. If this is set, the distribution needs to be deleted manually afterwards. | `bool` | `false` | no |
| tags | A map of tags to assign to the resource. | `map(string)` | `null` | no |
| viewer\_certificate | The SSL configuration for this distribution | `any` | ```{ "cloudfront_default_certificate": true, "minimum_protocol_version": "TLSv1" }``` | no |
| wait\_for\_deployment | If enabled, the resource will wait for the distribution status to change from InProgress to Deployed. Setting this to false will skip the process. | `bool` | `true` | no |
| web\_acl\_id | If you're using AWS WAF to filter CloudFront requests, the Id of the AWS WAF web ACL that is associated with the distribution. The WAF Web ACL must exist in the WAF Global (CloudFront) region and the credentials configuring this argument must have waf:GetWebACL permissions assigned. If using WAFv2, provide the ARN of the web ACL. | `string` | `null` | no |

## Outputs

| Name | Description |
|------|-------------|
| cloudfront\_distribution\_arn | The ARN (Amazon Resource Name) for the distribution. |
| cloudfront\_distribution\_caller\_reference | Internal value used by CloudFront to allow future updates to the distribution configuration. |
| cloudfront\_distribution\_domain\_name | The domain name corresponding to the distribution. |
| cloudfront\_distribution\_etag | The current version of the distribution's information. |
| cloudfront\_distribution\_hosted\_zone\_id | The CloudFront Route 53 zone ID that can be used to route an Alias Resource Record Set to. |
| cloudfront\_distribution\_id | The identifier for the distribution. |
| cloudfront\_distribution\_in\_progress\_validation\_batches | The number of invalidation batches currently in progress. |
| cloudfront\_distribution\_last\_modified\_time | The date and time the distribution was last modified. |
| cloudfront\_distribution\_status | The current status of the distribution. Deployed if the distribution's information is fully propagated throughout the Amazon CloudFront system. |
| cloudfront\_distribution\_tags | Tags of the distribution's |
| cloudfront\_distribution\_trusted\_signers | List of nested attributes for active trusted signers, if the distribution is set up to serve private content with signed URLs |
| cloudfront\_monitoring\_subscription\_id | The ID of the CloudFront monitoring subscription, which corresponds to the `distribution_id`. |
| cloudfront\_origin\_access\_controls | The origin access controls created |
| cloudfront\_origin\_access\_controls\_ids | The IDS of the origin access identities created |
| cloudfront\_origin\_access\_identities | The origin access identities created |
| cloudfront\_origin\_access\_identity\_iam\_arns | The IAM arns of the origin access identities created |
| cloudfront\_origin\_access\_identity\_ids | The IDS of the origin access identities created |
<!-- END_TF_DOCS -->
