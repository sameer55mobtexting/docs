# Click2Call

This Voice API supports the following:

#### HTTP Methods
  
  It will support both GET and POST requests.

## Call Initiation

#### POST/GET

C2C Using To as Mobile Number
```
{endpoint}voice/c2c?bridge=80191912XX&from=80106077XX&to=901930XXX
```
C2C Using To as Flow ID
```
{endpoint}voice/c2c?bridge=80191912XX&from=80106077XX&to=flow:19
```

####  MANDATORY PARAMETERS

| Name     | Descriptions |
|----------|--------------|
| bridge | DID number for call initiation |
| from | To whom call will connect first |
| to | Phone number / IVR flow to which call has to connect |


####  OPTIONAL PARAMETERS

| Name     | Descriptions |
|----------|--------------|
| mid |  Message id for reference |r |
| callback | Callback url once call completed |
| variables | `Array` of the variables which can be used in flow |
| record | Record this conversation (default `0`). allowed: 0 or 1 |

#### Example Request

```
curl -X GET \
  "{domain}/api/{{version}}/voice/c2c?access_token=209eccd40ee3a2e14af7fe45b21xxx&bridge=91801010XXX&from=9189195XXX&to=91901xxxxxx"
```

#### Example Response

```json
{
  "status": 200,
  "message": "Call initiated successfully",
}
```

####  CALLBACK REPLACEABLE VARIABLES

Callback is a functionality to get notified through an API call when a call is completed. One needs to follow below steps to achieve valid callback

| Name     | Descriptions |
|----------|--------------|
| bridge | DID number for call initiation |
| from | To whom call will connect first |
| to | Phone number / IVR flow to which call has to connect |
| start_at | Call Start time in `YYYY-MM-DD h:i:s` format |
| end_at | Call end time in `YYYY-MM-DD h:i:s` format |
| date | Current time in `YYYY-MM-DD h:i:s` format |
| unixtime | Current time in `unixtime` format |
| duration | Duration of the call in seconds (first call) |
| billing | Duration of the call in seconds (second call) |
| status | Call Status |
| status1 | Call Status of first call |
| status2 | Call Status of second call|
| recording_url | Recording Url if call got recorded |


You can also use our build in filters to change data while passing to your system.

Buildin filters are `cut` and `data_format`. Filters are seperated by `|`

Ex: if you want to get the last 10 digits of the `from` number: `{from|cut:-10}`

Ex: Want to get `start_at` date in `DD/MM/YYYY` : `{start_at|date_format:d/m/Y}`