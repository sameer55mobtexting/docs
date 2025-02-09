## Create Templates

Create templates using post method under your account

#### API Endpoint

```
{domain}/api/{version}/
```

#### POST

```
{endpoint}sms/templates
```

#### PARAMETERS

| Name        | Optional | Descriptions                                                     |
| ----------- | -------- | ---------------------------------------------------------------- |
| sender      | No       | Enter the approved sender-id under your account                  |
| name        | No       | Input the name of the template that you would like to refer with |
| body        | No       | Input the body of the sms(template)                              |
| template_id | Mixed    | DLT Template id (required for india)                             |
| type        | Mixed    | Type of the template like (P, T, SI, SE)(required for india)     |

#### Template types

| Template type | Description      |
| ------------- | ---------------- |
| T             | Transactional    |
| P             | Promotional      |
| SI            | Service Implicit |
| SE            | Service Explicit |

#### Example Request

```
curl -X POST \
  {endpoint}sms/templates \
    -H 'Accept: application/json' \
    -H 'Authorization: Bearer 5b02112fb7xxxxxxxxx'
    -H 'Content-Type: application/x-www-form-urlencoded' \
    -d sender=TXTsms \
    -d name=test1 \
    -d 'body=testing sms 1'
```

#### Example Response

```json
{
    "status": "OK",
    "code": 200,
    "message": "Template Saved Successfully",
    "data": {
        "id": "b23769e6-019f-48f4-aae9-ec00a5xxxxxx",
        "sender_id": "015c2f82-1352-4d19-9f8f-b8449xxxxxx",
        "template_id": "1107161521283358301",
        "template_type": "Transactional",
        "sender": "SENDER",
        "name": "hind-number",
        "body": "Your Verification code is:@{{1}} is code @{{2}}",
        "content": null,
        "body_length": 53,
        "match_count": 0,
        "percentage": 0,
        "is_complete": 0,
        "is_english": 1,
        "status": 1,
        "created_at": "2022-11-16T04:41:32.000000Z",
        "updated_at": "2022-11-16T04:41:32.000000Z"
    }
}
```
