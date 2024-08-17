# mm-sqs
This plugin is used to collect SQS queue data and configurations from an AWS account.

## Configuration
Configuration required to call and use this plugin in mist-miner.

```hcl
plug "mm-sqs" "custom group name" {
    authenticator = {
        profile = "aws profile name for accessing targeted account"
        // regions are optional, specify the desired regions for data collection, seperated by commas.
        // If not set, the default will include all available regions.
        regions = "us-east1,ap-northeast-1,..."
    }
}
```

## Resource collections

Collect SQS queue resource data using the AWS provided Golang [sdk](https://pkg.go.dev/github.com/aws/aws-sdk-go-v2/service/sqs).

### Queue methods with Get prefix
- :white_check_mark: **GetQueueAttributes:** Queue resource. Attribute property
- :warning: **GetQueueUrl:** Not implemented. Get urls with `ListQueues`

### Queue methods with List prefix
- :warning: **ListDeadLetterSourceQueues:** Not implemented. All queues are fetched with `ListQueues`
- :x: **ListMessageMoveTasks:** Not implemented, as it is deemed unnecessary for queue data collection
- :white_check_mark: **ListQueueTags:** Queue resource. Tag property
- :white_check_mark: **ListQueues:** Use `NewListQueuesPaginator` to retrieve all queues as resource for obtaining properties
