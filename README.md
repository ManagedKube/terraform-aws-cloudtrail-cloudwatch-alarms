
<!-- markdownlint-disable -->
# terraform-aws-cloudtrail-cloudwatch-alarms

 [![Build Status](https://travis-ci.org/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms.svg?branch=master)](https://travis-ci.org/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms) [![Latest Release](https://img.shields.io/github/release/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms.svg)](https://github.com/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/releases) [![Slack Community](https://slack.cloudposse.com/badge.svg)](https://slack.cloudposse.com)
<!-- markdownlint-restore -->

[![README Header][readme_header_img]][readme_header_link]

[![Cloud Posse][logo]](https://cpco.io/homepage)

<!--




  ** DO NOT EDIT THIS FILE
  **
  ** This file was automatically generated by the `build-harness`.
  ** 1) Make all changes to `README.yaml`
  ** 2) Run `make init` (you only need to do this once)
  ** 3) Run`make readme` to rebuild this file.
  **
  ** (We maintain HUNDREDS of open source projects. This is how we maintain our sanity.)
  **





-->

Terraform module for creating alarms for tracking important changes and occurances from cloudtrail.

This module creates a set of filter metrics and alarms based on the security best practices covered in the [AWS CIS Foundations Benchmark](https://d0.awsstatic.com/whitepapers/compliance/AWS_CIS_Foundations_Benchmark.pdf) guide.

---

This project is part of our comprehensive ["SweetOps"](https://cpco.io/sweetops) approach towards DevOps.
[<img align="right" title="Share via Email" src="https://docs.cloudposse.com/images/ionicons/ios-email-outline-2.0.1-16x16-999999.svg"/>][share_email]
[<img align="right" title="Share on Google+" src="https://docs.cloudposse.com/images/ionicons/social-googleplus-outline-2.0.1-16x16-999999.svg" />][share_googleplus]
[<img align="right" title="Share on Facebook" src="https://docs.cloudposse.com/images/ionicons/social-facebook-outline-2.0.1-16x16-999999.svg" />][share_facebook]
[<img align="right" title="Share on Reddit" src="https://docs.cloudposse.com/images/ionicons/social-reddit-outline-2.0.1-16x16-999999.svg" />][share_reddit]
[<img align="right" title="Share on LinkedIn" src="https://docs.cloudposse.com/images/ionicons/social-linkedin-outline-2.0.1-16x16-999999.svg" />][share_linkedin]
[<img align="right" title="Share on Twitter" src="https://docs.cloudposse.com/images/ionicons/social-twitter-outline-2.0.1-16x16-999999.svg" />][share_twitter]


[![Terraform Open Source Modules](https://docs.cloudposse.com/images/terraform-open-source-modules.svg)][terraform_modules]



It's 100% Open Source and licensed under the [APACHE2](LICENSE).







We literally have [*hundreds of terraform modules*][terraform_modules] that are Open Source and well-maintained. Check them out!






## Security & Compliance [<img src="https://cloudposse.com/wp-content/uploads/2020/11/bridgecrew.svg" width="250" align="right" />](https://bridgecrew.io/)

Security scanning is graciously provided by Bridgecrew. Bridgecrew is the leading fully hosted, cloud-native solution providing continuous Terraform security and compliance.

| Benchmark | Description |
|--------|---------------|
| [![Infrastructure Security](https://www.bridgecrew.cloud/badges/github/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/general)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=cloudposse%2Fterraform-aws-cloudtrail-cloudwatch-alarms&benchmark=INFRASTRUCTURE+SECURITY) | Infrastructure Security Compliance |
| [![CIS KUBERNETES](https://www.bridgecrew.cloud/badges/github/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/cis_kubernetes)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=cloudposse%2Fterraform-aws-cloudtrail-cloudwatch-alarms&benchmark=CIS+KUBERNETES+V1.5) | Center for Internet Security, KUBERNETES Compliance |
| [![CIS AWS](https://www.bridgecrew.cloud/badges/github/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/cis_aws)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=cloudposse%2Fterraform-aws-cloudtrail-cloudwatch-alarms&benchmark=CIS+AWS+V1.2) | Center for Internet Security, AWS Compliance |
| [![CIS AZURE](https://www.bridgecrew.cloud/badges/github/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/cis_azure)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=cloudposse%2Fterraform-aws-cloudtrail-cloudwatch-alarms&benchmark=CIS+AZURE+V1.1) | Center for Internet Security, AZURE Compliance |
| [![PCI-DSS](https://www.bridgecrew.cloud/badges/github/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/pci)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=cloudposse%2Fterraform-aws-cloudtrail-cloudwatch-alarms&benchmark=PCI-DSS+V3.2) | Payment Card Industry Data Security Standards Compliance |
| [![NIST-800-53](https://www.bridgecrew.cloud/badges/github/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/nist)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=cloudposse%2Fterraform-aws-cloudtrail-cloudwatch-alarms&benchmark=NIST-800-53) | National Institute of Standards and Technology Compliance |
| [![ISO27001](https://www.bridgecrew.cloud/badges/github/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/iso)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=cloudposse%2Fterraform-aws-cloudtrail-cloudwatch-alarms&benchmark=ISO27001) | Information Security Management System, ISO/IEC 27001 Compliance |
| [![SOC2](https://www.bridgecrew.cloud/badges/github/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/soc2)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=cloudposse%2Fterraform-aws-cloudtrail-cloudwatch-alarms&benchmark=SOC2)| Service Organization Control 2 Compliance |
| [![CIS GCP](https://www.bridgecrew.cloud/badges/github/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/cis_gcp)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=cloudposse%2Fterraform-aws-cloudtrail-cloudwatch-alarms&benchmark=CIS+GCP+V1.1) | Center for Internet Security, GCP Compliance |
| [![HIPAA](https://www.bridgecrew.cloud/badges/github/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/hipaa)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=cloudposse%2Fterraform-aws-cloudtrail-cloudwatch-alarms&benchmark=HIPAA) | Health Insurance Portability and Accountability Compliance |



## Usage


**IMPORTANT:** We do not pin modules to versions in our examples because of the
difficulty of keeping the versions in the documentation in sync with the latest released versions.
We highly recommend that in your code you pin the version to the exact version you are
using so that your infrastructure remains stable, and update versions in a
systematic way so that they do not catch you by surprise.

Also, because of a bug in the Terraform registry ([hashicorp/terraform#21417](https://github.com/hashicorp/terraform/issues/21417)),
the registry shows many of our inputs as required when in fact they are optional.
The table below correctly indicates which inputs are required.


```hcl
module "metric_configs" {
  source  = "cloudposse/config/yaml"
  # Cloud Posse recommends pinning every module to a specific version
  # version     = "x.x.x"

  map_config_local_base_path = "./catalog"
  map_config_paths           = "*.yaml"

  context = module.this.context
}

module "cloudtrail_api_alarms" {
  source  = "cloudposse/cloudtrail-cloudwatch-alarms/aws"
  # Cloud Posse recommends pinning every module to a specific version
  # version     = "x.x.x"

  log_group_name = "${aws_cloudwatch_log_group.default.name}"
  metrics = module.metric_configs.map_configs
}
```
For detailed usage which includes setting up cloudtrail, cloudwatch logs, roles, policies, and the s3 bucket - as well as using this module see the [example directory](./examples/complete)

For aditional CIS rules and controls https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-cis-controls.html#securityhub-cis-controls-3.8




## Examples

Here's a complete [example](examples/complete/main.tf) of using this `terraform-aws-cloudtrail-cloudwatch-alarms` module.



<!-- markdownlint-disable -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.13.0 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | >= 2.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | >= 2.0 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| <a name="module_aws_sns_topic_label"></a> [aws\_sns\_topic\_label](#module\_aws\_sns\_topic\_label) | cloudposse/label/null | 0.25.0 |
| <a name="module_sns_kms_key"></a> [sns\_kms\_key](#module\_sns\_kms\_key) | cloudposse/kms-key/aws | 0.10.0 |
| <a name="module_sns_kms_key_label"></a> [sns\_kms\_key\_label](#module\_sns\_kms\_key\_label) | cloudposse/label/null | 0.25.0 |
| <a name="module_this"></a> [this](#module\_this) | cloudposse/label/null | 0.25.0 |

## Resources

| Name | Type |
|------|------|
| [aws_cloudwatch_dashboard.combined](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_dashboard) | resource |
| [aws_cloudwatch_dashboard.individual](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_dashboard) | resource |
| [aws_cloudwatch_log_metric_filter.default](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_log_metric_filter) | resource |
| [aws_cloudwatch_metric_alarm.default](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_metric_alarm) | resource |
| [aws_sns_topic.default](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/sns_topic) | resource |
| [aws_sns_topic_policy.default](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/sns_topic_policy) | resource |
| [aws_caller_identity.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity) | data source |
| [aws_caller_identity.default](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity) | data source |
| [aws_iam_policy_document.sns_kms_key_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |
| [aws_iam_policy_document.sns_topic_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |
| [aws_region.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/region) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_additional_endpoint_arns"></a> [additional\_endpoint\_arns](#input\_additional\_endpoint\_arns) | Any alert endpoints, such as autoscaling, or app scaling endpoint arns that will respond to an alert | `list(string)` | `[]` | no |
| <a name="input_additional_tag_map"></a> [additional\_tag\_map](#input\_additional\_tag\_map) | Additional key-value pairs to add to each map in `tags_as_list_of_maps`. Not added to `tags` or `id`.<br>This is for some rare cases where resources want additional configuration of tags<br>and therefore take a list of maps with tag key, value, and additional configuration. | `map(string)` | `{}` | no |
| <a name="input_attributes"></a> [attributes](#input\_attributes) | ID element. Additional attributes (e.g. `workers` or `cluster`) to add to `id`,<br>in the order they appear in the list. New attributes are appended to the<br>end of the list. The elements of the list are joined by the `delimiter`<br>and treated as a single ID element. | `list(string)` | `[]` | no |
| <a name="input_context"></a> [context](#input\_context) | Single object for setting entire context at once.<br>See description of individual variables for details.<br>Leave string and numeric variables as `null` to use default value.<br>Individual variable settings (non-null) override settings in context object,<br>except for attributes, tags, and additional\_tag\_map, which are merged. | `any` | <pre>{<br>  "additional_tag_map": {},<br>  "attributes": [],<br>  "delimiter": null,<br>  "descriptor_formats": {},<br>  "enabled": true,<br>  "environment": null,<br>  "id_length_limit": null,<br>  "label_key_case": null,<br>  "label_order": [],<br>  "label_value_case": null,<br>  "labels_as_tags": [<br>    "unset"<br>  ],<br>  "name": null,<br>  "namespace": null,<br>  "regex_replace_chars": null,<br>  "stage": null,<br>  "tags": {},<br>  "tenant": null<br>}</pre> | no |
| <a name="input_dashboard_enabled"></a> [dashboard\_enabled](#input\_dashboard\_enabled) | When true a dashboard that displays the statistics as a line graph will be created in CloudWatch | `bool` | `true` | no |
| <a name="input_delimiter"></a> [delimiter](#input\_delimiter) | Delimiter to be used between ID elements.<br>Defaults to `-` (hyphen). Set to `""` to use no delimiter at all. | `string` | `null` | no |
| <a name="input_descriptor_formats"></a> [descriptor\_formats](#input\_descriptor\_formats) | Describe additional descriptors to be output in the `descriptors` output map.<br>Map of maps. Keys are names of descriptors. Values are maps of the form<br>`{<br>   format = string<br>   labels = list(string)<br>}`<br>(Type is `any` so the map values can later be enhanced to provide additional options.)<br>`format` is a Terraform format string to be passed to the `format()` function.<br>`labels` is a list of labels, in order, to pass to `format()` function.<br>Label values will be normalized before being passed to `format()` so they will be<br>identical to how they appear in `id`.<br>Default is `{}` (`descriptors` output will be empty). | `any` | `{}` | no |
| <a name="input_enabled"></a> [enabled](#input\_enabled) | Set to false to prevent the module from creating any resources | `bool` | `null` | no |
| <a name="input_environment"></a> [environment](#input\_environment) | ID element. Usually used for region e.g. 'uw2', 'us-west-2', OR role 'prod', 'staging', 'dev', 'UAT' | `string` | `null` | no |
| <a name="input_id_length_limit"></a> [id\_length\_limit](#input\_id\_length\_limit) | Limit `id` to this many characters (minimum 6).<br>Set to `0` for unlimited length.<br>Set to `null` for keep the existing setting, which defaults to `0`.<br>Does not affect `id_full`. | `number` | `null` | no |
| <a name="input_kms_master_key_id"></a> [kms\_master\_key\_id](#input\_kms\_master\_key\_id) | The ID or alias of the customer master key (CMK) to use for encrypting the Amazon SNS topic.<br>  The CMK must have its resource-based policy allow the service `cloudwatch.amazonaws.com` to perform `kms:Decrypt` and `kms:GenerateDataKey` on it.<br>  If this variable is not supplied, a CMK with the sufficient resource-based policy will be created and used when configuring encryption for<br>  the SNS topic. | `string` | `null` | no |
| <a name="input_label_key_case"></a> [label\_key\_case](#input\_label\_key\_case) | Controls the letter case of the `tags` keys (label names) for tags generated by this module.<br>Does not affect keys of tags passed in via the `tags` input.<br>Possible values: `lower`, `title`, `upper`.<br>Default value: `title`. | `string` | `null` | no |
| <a name="input_label_order"></a> [label\_order](#input\_label\_order) | The order in which the labels (ID elements) appear in the `id`.<br>Defaults to ["namespace", "environment", "stage", "name", "attributes"].<br>You can omit any of the 6 labels ("tenant" is the 6th), but at least one must be present. | `list(string)` | `null` | no |
| <a name="input_label_value_case"></a> [label\_value\_case](#input\_label\_value\_case) | Controls the letter case of ID elements (labels) as included in `id`,<br>set as tag values, and output by this module individually.<br>Does not affect values of tags passed in via the `tags` input.<br>Possible values: `lower`, `title`, `upper` and `none` (no transformation).<br>Set this to `title` and set `delimiter` to `""` to yield Pascal Case IDs.<br>Default value: `lower`. | `string` | `null` | no |
| <a name="input_labels_as_tags"></a> [labels\_as\_tags](#input\_labels\_as\_tags) | Set of labels (ID elements) to include as tags in the `tags` output.<br>Default is to include all labels.<br>Tags with empty values will not be included in the `tags` output.<br>Set to `[]` to suppress all generated tags.<br>**Notes:**<br>  The value of the `name` tag, if included, will be the `id`, not the `name`.<br>  Unlike other `null-label` inputs, the initial setting of `labels_as_tags` cannot be<br>  changed in later chained modules. Attempts to change it will be silently ignored. | `set(string)` | <pre>[<br>  "default"<br>]</pre> | no |
| <a name="input_log_group_name"></a> [log\_group\_name](#input\_log\_group\_name) | The cloudtrail cloudwatch log group name | `string` | n/a | yes |
| <a name="input_log_group_region"></a> [log\_group\_region](#input\_log\_group\_region) | The log group region that should be monitored for unauthorised AWS API Access. Current region used if none provided. | `string` | `""` | no |
| <a name="input_metric_namespace"></a> [metric\_namespace](#input\_metric\_namespace) | A namespace for grouping all of the metrics together | `string` | `"CISBenchmark"` | no |
| <a name="input_metrics"></a> [metrics](#input\_metrics) | The cloudwatch metrics and corresponding alarm definitions | <pre>map(object({<br>    metric_name               = string<br>    filter_pattern            = string<br>    metric_namespace          = string<br>    metric_value              = string<br>    alarm_name                = string<br>    alarm_comparison_operator = string<br>    alarm_evaluation_periods  = string<br>    alarm_period              = string<br>    alarm_statistic           = string<br>    alarm_treat_missing_data  = string<br>    alarm_threshold           = string<br>    alarm_description         = string<br>  }))</pre> | `{}` | no |
| <a name="input_name"></a> [name](#input\_name) | ID element. Usually the component or solution name, e.g. 'app' or 'jenkins'.<br>This is the only ID element not also included as a `tag`.<br>The "name" tag is set to the full `id` string. There is no tag with the value of the `name` input. | `string` | `null` | no |
| <a name="input_namespace"></a> [namespace](#input\_namespace) | ID element. Usually an abbreviation of your organization name, e.g. 'eg' or 'cp', to help ensure generated IDs are globally unique | `string` | `null` | no |
| <a name="input_regex_replace_chars"></a> [regex\_replace\_chars](#input\_regex\_replace\_chars) | Terraform regular expression (regex) string.<br>Characters matching the regex will be removed from the ID elements.<br>If not set, `"/[^a-zA-Z0-9-]/"` is used to remove all characters other than hyphens, letters and digits. | `string` | `null` | no |
| <a name="input_sns_policy_enabled"></a> [sns\_policy\_enabled](#input\_sns\_policy\_enabled) | Attach a policy that allows the notifications through to the SNS topic endpoint | `bool` | `false` | no |
| <a name="input_sns_topic_arn"></a> [sns\_topic\_arn](#input\_sns\_topic\_arn) | An SNS topic ARN that has already been created. Its policy must already allow access from CloudWatch Alarms, or set `add_sns_policy` to `true` | `string` | `null` | no |
| <a name="input_stage"></a> [stage](#input\_stage) | ID element. Usually used to indicate role, e.g. 'prod', 'staging', 'source', 'build', 'test', 'deploy', 'release' | `string` | `null` | no |
| <a name="input_tags"></a> [tags](#input\_tags) | Additional tags (e.g. `{'BusinessUnit': 'XYZ'}`).<br>Neither the tag keys nor the tag values will be modified by this module. | `map(string)` | `{}` | no |
| <a name="input_tenant"></a> [tenant](#input\_tenant) | ID element \_(Rarely used, not included by default)\_. A customer identifier, indicating who this instance of a resource is for | `string` | `null` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_dashboard_combined"></a> [dashboard\_combined](#output\_dashboard\_combined) | URL to CloudWatch Combined Metric Dashboard |
| <a name="output_dashboard_individual"></a> [dashboard\_individual](#output\_dashboard\_individual) | URL to CloudWatch Individual Metric Dashboard |
| <a name="output_sns_topic_arn"></a> [sns\_topic\_arn](#output\_sns\_topic\_arn) | The ARN of the SNS topic used |
<!-- markdownlint-restore -->
## Metrics Tracked

|  Alarm's Name |  Description       |
|:--------------|:-------------------|
|  `AuthorizationFailureCount`       |  Alarms when an unauthorized API call is made.  |
|  `S3BucketActivityEventCount`      |  Alarms when an API call is made to S3 to put or delete a Bucket, Bucket Policy or Bucket ACL.  |
|  `SecurityGroupEventCount`         |  Alarms when an API call is made to create, update or delete a Security Group.  |
|  `NetworkAclEventCount`            |  Alarms when an API call is made to create, update or delete a Network ACL.  |
|  `GatewayEventCount`               |  Alarms when an API call is made to create, update or delete a Customer or Internet Gateway.  |
|  `VpcEventCount`                   |  Alarms when an API call is made to create, update or delete a VPC, VPC peering connection or VPC connection to classic.  |
|  `EC2InstanceEventCount`           |  Alarms when an API call is made to create, terminate, start, stop or reboot an EC2 instance.  |
|  `EC2LargeInstanceEventCount`      |  Alarms when an API call is made to create, terminate, start, stop or reboot a 4x-large or greater EC2 instance.  |
|  `CloudTrailEventCount`            |  Alarms when an API call is made to create, update or delete a .cloudtrail. trail, or to start or stop logging to a trail.  |
|  `ConsoleSignInFailureCount`       |  Alarms when an unauthenticated API call is made to sign into the console.  |
|  `IAMPolicyEventCount`             |  Alarms when an API call is made to change an IAM policy.   |
|  `ConsoleSignInWithoutMfaCount`    |  Alarms when a user logs into the console without MFA.   |
|  `RootAccountUsageCount`           |  Alarms when a root account usage is detected.   |
|  `KMSKeyPendingDeletionErrorCount` |  Alarms when a customer created KMS key is pending deletion.    |
|  `AWSConfigChangeCount`            |  Alarms when AWS Config changes.   |
|  `RouteTableChangesCount`          |  Alarms when route table changes are detected.   |

## Dashboard Created

Two CloudWatch Dashboards can be created as well, and will be automatically created by default.

![CloudWatch Dashboard](docs/screen1.png)

## Credits

The alarm metric names, descriptions, and filters [from this repository were used](https://github.com/TeliaSoneraNorge/telia-terraform-modules/tree/master/cloudtrail-forwarder).

With many thanks to [Anton Babenko](https://github.com/antonbabenko) for pointing it out and saving us a lot of time scouring reference documents and describing alarms!





## Share the Love

Like this project? Please give it a ★ on [our GitHub](https://github.com/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms)! (it helps us **a lot**)

Are you using this project or any of our other projects? Consider [leaving a testimonial][testimonial]. =)



## Related Projects

Check out these related projects.

- [terraform-aws-cloudtrail](https://github.com/cloudposse/terraform-aws-cloudtrail) - Terraform module to provision an AWS CloudTrail and an encrypted S3 bucket with versioning to store CloudTrail logs
- [terraform-aws-cloudtrail-s3-bucket](https://github.com/cloudposse/terraform-aws-cloudtrail-s3-bucket) - S3 bucket with built in IAM policy to allow CloudTrail logs
- [terraform-aws-cloudwatch-logs](https://github.com/cloudposse/terraform-aws-cloudwatch-logs) - Terraform Module to Provide a CloudWatch Logs Endpoint
- [terraform-aws-cloudwatch-flow-logs](https://github.com/cloudposse/terraform-aws-cloudwatch-flow-logs) - Terraform module for enabling flow logs for vpc and subnets.
- [terraform-aws-ec2-cloudwatch-sns-alarms](https://github.com/cloudposse/terraform-aws-ec2-cloudwatch-sns-alarms) - Terraform module that configures CloudWatch SNS alerts for EC2 instances
- [terraform-aws-ecs-cloudwatch-sns-alarms](https://github.com/cloudposse/terraform-aws-ecs-cloudwatch-sns-alarms) - Terraform module for creating ECS service level alerts that go to an SNS endpoint
- [terraform-aws-efs-cloudwatch-sns-alarms](https://github.com/cloudposse/terraform-aws-efs-cloudwatch-sns-alarms) - Terraform module that configures CloudWatch SNS alerts for EFS
- [terrform-aws-elasticache-cloudwatch-sns-alarms](https://github.com/cloudposse/terraform-aws-elasticache-cloudwatch-sns-alarms) - Terraform module that configures CloudWatch SNS alerts for ElastiCache
- [terraform-aws-lambda-cloudwatch-sns-alarms](https://github.com/cloudposse/terraform-aws-lambda-cloudwatch-sns-alarms) - Terraform module for creating a set of Lambda alarms and outputting to an endpoint
- [terraform-aws-rds-cloudwatch-sns-alarms](https://github.com/cloudposse/terraform-aws-rds-cloudwatch-sns-alarms) - Terraform module that configures important RDS alerts using CloudWatch and sends them to an SNS topic
- [terraform-aws-sqs-cloudwatch-sns-alarms](https://github.com/cloudposse/terraform-aws-sqs-cloudwatch-sns-alarms) - Terraform module for creating alarms for SQS and notifying endpoints

## Help

**Got a question?** We got answers.

File a GitHub [issue](https://github.com/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/issues), send us an [email][email] or join our [Slack Community][slack].

[![README Commercial Support][readme_commercial_support_img]][readme_commercial_support_link]

## DevOps Accelerator for Startups


We are a [**DevOps Accelerator**][commercial_support]. We'll help you build your cloud infrastructure from the ground up so you can own it. Then we'll show you how to operate it and stick around for as long as you need us.

[![Learn More](https://img.shields.io/badge/learn%20more-success.svg?style=for-the-badge)][commercial_support]

Work directly with our team of DevOps experts via email, slack, and video conferencing.

We deliver 10x the value for a fraction of the cost of a full-time engineer. Our track record is not even funny. If you want things done right and you need it done FAST, then we're your best bet.

- **Reference Architecture.** You'll get everything you need from the ground up built using 100% infrastructure as code.
- **Release Engineering.** You'll have end-to-end CI/CD with unlimited staging environments.
- **Site Reliability Engineering.** You'll have total visibility into your apps and microservices.
- **Security Baseline.** You'll have built-in governance with accountability and audit logs for all changes.
- **GitOps.** You'll be able to operate your infrastructure via Pull Requests.
- **Training.** You'll receive hands-on training so your team can operate what we build.
- **Questions.** You'll have a direct line of communication between our teams via a Shared Slack channel.
- **Troubleshooting.** You'll get help to triage when things aren't working.
- **Code Reviews.** You'll receive constructive feedback on Pull Requests.
- **Bug Fixes.** We'll rapidly work with you to fix any bugs in our projects.

## Slack Community

Join our [Open Source Community][slack] on Slack. It's **FREE** for everyone! Our "SweetOps" community is where you get to talk with others who share a similar vision for how to rollout and manage infrastructure. This is the best place to talk shop, ask questions, solicit feedback, and work together as a community to build totally *sweet* infrastructure.

## Discourse Forums

Participate in our [Discourse Forums][discourse]. Here you'll find answers to commonly asked questions. Most questions will be related to the enormous number of projects we support on our GitHub. Come here to collaborate on answers, find solutions, and get ideas about the products and services we value. It only takes a minute to get started! Just sign in with SSO using your GitHub account.

## Newsletter

Sign up for [our newsletter][newsletter] that covers everything on our technology radar.  Receive updates on what we're up to on GitHub as well as awesome new projects we discover.

## Office Hours

[Join us every Wednesday via Zoom][office_hours] for our weekly "Lunch & Learn" sessions. It's **FREE** for everyone!

[![zoom](https://img.cloudposse.com/fit-in/200x200/https://cloudposse.com/wp-content/uploads/2019/08/Powered-by-Zoom.png")][office_hours]

## Contributing

### Bug Reports & Feature Requests

Please use the [issue tracker](https://github.com/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms/issues) to report any bugs or file feature requests.

### Developing

If you are interested in being a contributor and want to get involved in developing this project or [help out](https://cpco.io/help-out) with our other projects, we would love to hear from you! Shoot us an [email][email].

In general, PRs are welcome. We follow the typical "fork-and-pull" Git workflow.

 1. **Fork** the repo on GitHub
 2. **Clone** the project to your own machine
 3. **Commit** changes to your own branch
 4. **Push** your work back up to your fork
 5. Submit a **Pull Request** so that we can review your changes

**NOTE:** Be sure to merge the latest changes from "upstream" before making a pull request!


## Copyright

Copyright © 2017-2021 [Cloud Posse, LLC](https://cpco.io/copyright)



## License

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

See [LICENSE](LICENSE) for full details.

```text
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

  https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
```









## Trademarks

All other trademarks referenced herein are the property of their respective owners.

## About

This project is maintained and funded by [Cloud Posse, LLC][website]. Like it? Please let us know by [leaving a testimonial][testimonial]!

[![Cloud Posse][logo]][website]

We're a [DevOps Professional Services][hire] company based in Los Angeles, CA. We ❤️  [Open Source Software][we_love_open_source].

We offer [paid support][commercial_support] on all of our projects.

Check out [our other projects][github], [follow us on twitter][twitter], [apply for a job][jobs], or [hire us][hire] to help with your cloud strategy and implementation.



### Contributors

<!-- markdownlint-disable -->
|  [![Erik Osterman][osterman_avatar]][osterman_homepage]<br/>[Erik Osterman][osterman_homepage] | [![Jamie Nelson][Jamie-BitFlight_avatar]][Jamie-BitFlight_homepage]<br/>[Jamie Nelson][Jamie-BitFlight_homepage] | [![Anton Babenko][antonbabenko_avatar]][antonbabenko_homepage]<br/>[Anton Babenko][antonbabenko_homepage] | [![PePe Amengual][jamengual_avatar]][jamengual_homepage]<br/>[PePe Amengual][jamengual_homepage] |
|---|---|---|---|
<!-- markdownlint-restore -->


  [osterman_homepage]: https://github.com/osterman
  [osterman_avatar]: http://s.gravatar.com/avatar/88c480d4f73b813904e00a5695a454cb?s=144


  [Jamie-BitFlight_homepage]: https://github.com/Jamie-BitFlight
  [Jamie-BitFlight_avatar]: https://avatars0.githubusercontent.com/u/25075504?s=144&u=ac7e53bda3706cb9d51907808574b6d342703b3e&v=4


  [antonbabenko_homepage]: https://github.com/antonbabenko
  [antonbabenko_avatar]: https://avatars3.githubusercontent.com/u/393243?s=144&v=4

  [jamengual_homepage]: https://github.com/jamengual
  [jamengual_avatar]: https://avatars.githubusercontent.com/u/2208324?s=144&v=4


[![README Footer][readme_footer_img]][readme_footer_link]
[![Beacon][beacon]][website]

  [logo]: https://cloudposse.com/logo-300x69.svg
  [docs]: https://cpco.io/docs?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=docs
  [website]: https://cpco.io/homepage?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=website
  [github]: https://cpco.io/github?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=github
  [jobs]: https://cpco.io/jobs?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=jobs
  [hire]: https://cpco.io/hire?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=hire
  [slack]: https://cpco.io/slack?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=slack
  [linkedin]: https://cpco.io/linkedin?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=linkedin
  [twitter]: https://cpco.io/twitter?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=twitter
  [testimonial]: https://cpco.io/leave-testimonial?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=testimonial
  [office_hours]: https://cloudposse.com/office-hours?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=office_hours
  [newsletter]: https://cpco.io/newsletter?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=newsletter
  [discourse]: https://ask.sweetops.com/?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=discourse
  [email]: https://cpco.io/email?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=email
  [commercial_support]: https://cpco.io/commercial-support?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=commercial_support
  [we_love_open_source]: https://cpco.io/we-love-open-source?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=we_love_open_source
  [terraform_modules]: https://cpco.io/terraform-modules?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=terraform_modules
  [readme_header_img]: https://cloudposse.com/readme/header/img
  [readme_header_link]: https://cloudposse.com/readme/header/link?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=readme_header_link
  [readme_footer_img]: https://cloudposse.com/readme/footer/img
  [readme_footer_link]: https://cloudposse.com/readme/footer/link?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=readme_footer_link
  [readme_commercial_support_img]: https://cloudposse.com/readme/commercial-support/img
  [readme_commercial_support_link]: https://cloudposse.com/readme/commercial-support/link?utm_source=github&utm_medium=readme&utm_campaign=cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms&utm_content=readme_commercial_support_link
  [share_twitter]: https://twitter.com/intent/tweet/?text=terraform-aws-cloudtrail-cloudwatch-alarms&url=https://github.com/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms
  [share_linkedin]: https://www.linkedin.com/shareArticle?mini=true&title=terraform-aws-cloudtrail-cloudwatch-alarms&url=https://github.com/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms
  [share_reddit]: https://reddit.com/submit/?url=https://github.com/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms
  [share_facebook]: https://facebook.com/sharer/sharer.php?u=https://github.com/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms
  [share_googleplus]: https://plus.google.com/share?url=https://github.com/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms
  [share_email]: mailto:?subject=terraform-aws-cloudtrail-cloudwatch-alarms&body=https://github.com/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms
  [beacon]: https://ga-beacon.cloudposse.com/UA-76589703-4/cloudposse/terraform-aws-cloudtrail-cloudwatch-alarms?pixel&cs=github&cm=readme&an=terraform-aws-cloudtrail-cloudwatch-alarms
