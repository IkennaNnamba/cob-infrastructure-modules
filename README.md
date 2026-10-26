# cob-modules

Shared Terraform modules for the COB platform, owned by Platform Engineering.
Consumed by the `cob-live` repo, always pinned to a released version tag.

## Modules

| Module | Purpose |
|---|---|
| `networking` | VPC, subnets, IGW, optional NAT, route tables, baseline security group |
| `iam` | Workload role with trust policy and inline policy |
| `object-storage` | S3 with KMS, versioning, public-access block, lifecycle |
| `compute-ec2` | EC2 with closed-by-default security group, encrypted root volume |
| `compute-ecs` | ECS/Fargate cluster, service, task definition, circuit breaker |
| `relational-database` | RDS with Secrets Manager credentials |
| `data-catalog` | Glue database and crawler, Athena workgroup |

Usage docs for each module are in `docs/modules/`.

## Usage

Always pin to a tag, never a branch:

```hcl
module "networking" {
  source = "git::https://github.com/IkennaNnamba/cob-modules.git//modules/networking?ref=v1.0.0"
  # inputs...
}
```

## Versioning

Semantic versioning. Patch = bug fix, minor = backward-compatible feature,
major = breaking change (renamed or removed inputs, resource replacement).
