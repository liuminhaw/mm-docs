# mm-s3
This module is used to collect S3 bucket data and configurations from an AWS account.

## Configuration
Configuration required to call and use this module in mist-miner.

```hcl
plug "mm-s3" "custom group name" {
    authenticator = {
        profile = "aws profile name for accessing targeted account"
    }
}
```

## Notes
Directory buckets are not supported in this module currently.

## Resource collections

Collected S3 bucket resource data from AWS provided golang
[sdk](https://pkg.go.dev/github.com/aws/aws-sdk-go-v2/service/s3).

### Bucket methods with Get prefix
- :white_check_mark: **GetBucketAccelerateConfiguration:** Bucket resource.
  Accelerate config property
- :white_check_mark: **GetBucketAcl:** Bucket resource. Acl property
- :warning: **GetBucketAnalyticsConfigurationInput:** Not implemented. Get settings with `ListBucketAnalyticsConfigurations`
- :white_check_mark: **GetBucketCors:** Bucket resource. CORS property
- :white_check_mark: **GetBucketEncryption:** Bucket resource. Encryption property
- :warning: **GetBucketIntelligentTieringConfiguration:** Not implemented. Get settings with `ListBucketIntelligentTieringConfigurations`
- :warning: **GetBucketInventoryConfiguration:** Not implemented. Get settings with `ListBucketInventoryConfigurations`
- :white_check_mark: **GetBucketLifecycleConfiguration:** Bucket resource. Lifecycle property
- :white_check_mark: **GetBucketLocation:** Bucket resource. Location property
- :white_check_mark: **GetBucketLogging:** Bucket resource. Logging property
- :warning: **GetBucketMetricsConfiguration:** Not implemented. Get settings with `ListBucketMetricsConfigurations`
- :white_check_mark: **GetBucketNotificationConfiguration:** Bucket resource. Notification property
- :white_check_mark: **GetBucketOwnershipControls:** Bucket resource. OwnershipControl property
- :white_check_mark: **GetBucketPolicy:** Bucket resource. Policy property
- :white_check_mark: **GetBucketPolicyStatus:** Bucket resource. PolicyStatus property
- :white_check_mark: **GetBucketReplication:** Bucket resource. Replication property
- :white_check_mark: **GetBucketRequestPayment:** Bucket resource. RequestPayment property
- :white_check_mark: **GetBucketTagging:** Bucket resource. Tag property
- :white_check_mark: **GetBucketVersioning:** Bucket resource. Versioning property
- :white_check_mark: **GetBucketWebsite:** Bucket resource. Website property

### Bucket methods with List prefix
- :white_check_mark: **ListBucketAnalyticsConfigurations:** Bucket resource. AnalyticsConfig property
- :white_check_mark: **ListBucketIntelligentTieringConfigurations:** Bucket resource. IntelligentTiering property
- :white_check_mark: **ListBucketInventoryConfigurations:** Bucket resource. Inventory property
- :white_check_mark: **ListBucketMetricsConfigurations:** Bucket resource. Metrics property
- :white_check_mark: **ListBuckets:** Use for getting all buckets, not for fetching bucket properties
