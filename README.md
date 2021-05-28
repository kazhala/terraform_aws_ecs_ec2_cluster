# terraform-aws-ecs-ec2-cluster

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | >= 3.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | >= 3.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_autoscaling_group.ecs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/autoscaling_group) | resource |
| [aws_ecs_cluster.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecs_cluster) | resource |
| [aws_iam_instance_profile.ecs_agent](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_instance_profile) | resource |
| [aws_iam_role.ecs_agent](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [aws_iam_role_policy_attachment.ecs_agent](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role_policy_attachment) | resource |
| [aws_launch_configuration.ecs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_configuration) | resource |
| [aws_iam_policy_document.ecs_assume_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |
| [aws_ssm_parameter.ecs_ami](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ssm_parameter) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_additional_user_data"></a> [additional\_user\_data](#input\_additional\_user\_data) | Additional user data to apply to the ECS instance Launch Configuration. | `string` | `""` | no |
| <a name="input_container_insights"></a> [container\_insights](#input\_container\_insights) | Enable ECS container insights. Allowed values: enabled \| disabled. | `string` | `"disabled"` | no |
| <a name="input_desired_capacity"></a> [desired\_capacity](#input\_desired\_capacity) | Desired number of instances for the cluster. | `number` | `1` | no |
| <a name="input_encrypted"></a> [encrypted](#input\_encrypted) | Encrypt EC2 instance ebs volume. | `bool` | `false` | no |
| <a name="input_health_check_grace_period"></a> [health\_check\_grace\_period](#input\_health\_check\_grace\_period) | Grace period between each scaling activity for EC2 instances in the ECS cluster. | `number` | `300` | no |
| <a name="input_health_check_type"></a> [health\_check\_type](#input\_health\_check\_type) | Health checking method. Allowed values: ELB \| EC2. | `string` | `"EC2"` | no |
| <a name="input_image_id"></a> [image\_id](#input\_image\_id) | ECS instance image id. If not provided, the latest Linux Amazon ECS-optimized AMI will be used. | `string` | `null` | no |
| <a name="input_instance_type"></a> [instance\_type](#input\_instance\_type) | The EC2 instance type to launch for the ECS cluster. | `string` | `"t3.micro"` | no |
| <a name="input_load_balancers"></a> [load\_balancers](#input\_load\_balancers) | List of ELB names to attach to the cluster, for ALB use target\_group\_arns. | `list(string)` | `null` | no |
| <a name="input_max_size"></a> [max\_size](#input\_max\_size) | Maximum number of instances for the cluster. | `number` | `1` | no |
| <a name="input_min_size"></a> [min\_size](#input\_min\_size) | Minimum number of instances for the cluster. | `number` | `1` | no |
| <a name="input_name"></a> [name](#input\_name) | The Name of the ECS cluster. | `string` | n/a | yes |
| <a name="input_security_groups"></a> [security\_groups](#input\_security\_groups) | List of Security Group ARNs to attach to the ECS cluster EC2 instance. | `list(string)` | `null` | no |
| <a name="input_subnets"></a> [subnets](#input\_subnets) | List of subnet ids to deploy the ECS cluster.<br>Subnets should have outbound internet access as the ECS agent require internet access. | `list(string)` | n/a | yes |
| <a name="input_tags"></a> [tags](#input\_tags) | Additional resource tags to apply to applicable resources. Format: {"key" = "value"} | `map(string)` | `{}` | no |
| <a name="input_target_group_arns"></a> [target\_group\_arns](#input\_target\_group\_arns) | List of Target Groups to attach to the cluster, for ELB use load\_balancers. | `list(string)` | `null` | no |
| <a name="input_vpc_id"></a> [vpc\_id](#input\_vpc\_id) | The ID of the VPC to deploy the ECS cluster. | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_asg_arn"></a> [asg\_arn](#output\_asg\_arn) | The ARN of the Auto Scaling Group. |
| <a name="output_asg_id"></a> [asg\_id](#output\_asg\_id) | The ID of the Auto Scaling Group. |
| <a name="output_asg_name"></a> [asg\_name](#output\_asg\_name) | The Name of the Auto Scaling Group. |
| <a name="output_cluster_arn"></a> [cluster\_arn](#output\_cluster\_arn) | The ARN of the ECS cluster. |
| <a name="output_cluster_id"></a> [cluster\_id](#output\_cluster\_id) | The ID of the ECS cluster. |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
