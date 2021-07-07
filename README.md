# terraform-lambda-memory-monitoring
Terraform module which sends memory usage alerts to SNS Topic via CloudWatch Log Metric Filter

## Terraform versions

For terraform 0.11 use release v1.0.0, for terraform 0.12+ use v2.0.0

## Usage
```hcl
module "some-unique-identifier" {
  source = "github.com/bskim45/terraform-lambda-memory-monitoring?ref=v1.0.0"

  function_name      = "lambda-function-name"
  sns_topic_name     = "sns-topic-name"
  metrics_namespace  = "ConcurrencyLabs/Lambda/"
  threshold_percent  = 70
  period             = 60
  evaluation_periods = 1

  tags = {
    "Environment" = "dev"
  }
}
```

## License

Apache 2.0 licensed. See [LICENSE](LICENSE) for full details.
