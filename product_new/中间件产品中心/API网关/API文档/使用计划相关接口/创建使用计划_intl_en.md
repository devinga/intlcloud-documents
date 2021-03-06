## API Description

This API (CreateUsagePlan) is used to create a usage plan.
To use API Gateway, you need to create a usage plan and bind it to a service environment.

## Input Parameters

The list below contains only the API request parameters. Other parameters can be found in [Common Request Parameters](https://intl.cloud.tencent.com/document/api/213/6976).

| Parameter Name | Required | Type | Description |
| ------------------- | ---- | ------ | -------------- |
| usagePlanName | No | String | User-defined usage plan name |
| usagePlanDesc | No | String | User-defined usage plan description |
| maxRequestNumPreSec | No | Int | Limit of requests per second. Default value: 1,000 |
| maxRequestNum | No | Int | Total number of requests allowed. If this is left empty, -1 will be used by default, indicating it’s disabled |

## Output Parameters

| Parameter Name | Type | Description |
| ------------- | --------- | ------------------------------------------------------------ |
| code | Int | Common error code. 0: success; other values: failure. For more information, see [Common Error Codes](https://intl.cloud.tencent.com/document/product/377/8946) |
| codeDesc | String | Description of the action status. When the action has succeeded, "Success" is returned. When the action has failed, a message describing the cause of the error is returned. |
| message | String | API-related module error message description. |
| UsagePlanId | String | Usage plan ID, which is generated by the system and globally unique |
| UsagePlanName | String | User-defined usage plan name |
| UsagePlanDesc | String | User-defined usage plan description |
| createdTime | Timestamp | Creation time in the format of YYYY-MM-DDThh:mm:ssZ according to ISO8601 standard. UTC time is used |

## Samples 
```
https://apigateway.api.qcloud.com/v2/index.php?
&<Common Request Parameter>
&Action=CreateUsagePlan
&usagePlanName=test
&usagePlanDesc=testDesc
&maxRequestNumPreSec=100
```
Below is a sample return:
```
{
	"code": "0",
	"message": "",
	"codeDesc": "Success",
	"usagePlanId": "usagePlan-XX",
	"usagePlanName": "name",
	"usagePlanDesc": "desc",
	"createdTime": "2017-08-07T00:00:00Z"
}
```
