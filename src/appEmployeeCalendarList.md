# appEmployeeCalendarList
取得特定員工行事曆資訊

### HTTP Request
```
https://114.34.125.246:8090/servlet/HRNative/appEmployeeCalendarList
```

### HTTP Request Mehod
```
POST
```

### Request body
| Key | Value | Type | Description |
|:----------|:-------------|:-----|:------------|
| uid | 98599308101484732326 | String | 需透過appLogin取得
| right | 51341911904173543336756162544864820 | String | 需透過appLogin取得 |
| request | {empid:admin, eventYM:202111, eventStartDate:20211101, eventEndDate:20211130, eventDate:20211130} | Object | 查詢條件

### JSON representation
Case 1 . Here is a JSON representation of request. 
```json
{
    "uid":"98599308101484732326",
    "right":"51341911904173543336756162544864820",
    "request":{
        "empid":"admin",
        "eventStartDate":"20211101",
        "eventEndDate":"20211130"
    }
}
```
Case 2 . Here is a JSON representation of request. 
```json
{
    "uid":"98599308101484732326",
    "right":"51341911904173543336756162544864820",
    "request":{
        "empid":"admin",
        "eventYM":"202111"
    }
}
```
Case 3 . Here is a JSON representation of request. 
```json
{
    "uid":"98599308101484732326",
    "right":"51341911904173543336756162544864820",
    "request":{
        "empid":"admin",
        "eventDate":"20211101",
    }
}
```

### Properties
| Property | Type | Description |
|:---------|:-----|:------------|
| uid   | String | 加密後帳號 |
| right | String | 加密後系統相關資料 |
| request | Object | 要求本文 |

### Request Properties
| Case No | Key | Value | Type | Description | Required | Format |
|:----------|:----------|:-------------|:-----|:------------|:------------|:------------|
| 1 | empid | admin | String | 員工編號 | Y | n/a |
|   | eventStartDate | 20211101 | String | 事件起始日期 | N | AC(YYYYmmdd) |
|   | eventEndDate | 20211130 | String | 事件結束日期 | N | AC(YYYYmmdd) |
| 2 | empid | admin | String | 員工編號 | Y | n/a |
|   | eventYM | 202111 | String | 事件年月 | N | AC(YYYYmm) |
| 3 | empid | admin | String | 員工編號 | Y | n/a |
|   | eventDate | 20211130 | String | 事件日期 | N | AC(YYYYmmdd) |

### HTTP Response when Successful
```json
{
   "status":"success",
   "message":[
      "回傳成功"
   ],
   "data":{
      "employeeCalendarList":{
         "id":"employeeCalendarList",
         "name":"員工個人行事曆列表",
         "value":[
            {
               "seriesNo":{
                  "id":"seriesNo",
                  "name":"行事曆編號",
                  "value":"XXXXXXXXXXXXXX",
                  "type":"string",
                  "format":"n/a"
               },
               "empid":{
                  "id":"empid",
                  "name":"員工編號",
                  "value":"L100387",
                  "type":"string",
                  "format":"n/a"
               },
               "eventBeginDate":{
                  "id":"eventBeginDate",
                  "name":"事件起始日期",
                  "value":"20211123",
                  "type":"string",
                  "format":"YYYYmmdd"
               },
               "eventEndDate":{
                  "id":"eventEndDate",
                  "name":"事件結束日期",
                  "value":"20211123",
                  "type":"string",
                  "format":"YYYYmmdd"
               },
               "isFullDayEvent":{
                  "id":"isFullDayEvent",
                  "name":"是否為全天候事件",
                  "value":true,
                  "type":"boolean",
                  "format":"n/a"
               },
               "eventBeginTime":{
                  "id":"eventBeginTime",
                  "name":"事件起始時間",
                  "value":"0900",
                  "type":"string",
                  "format":"HHmm"
               },
               "eventEndTime":{
                  "id":"eventEndTime",
                  "name":"事件結束時間",
                  "value":"1500",
                  "type":"string",
                  "format":"HHmm"
               },
               "eventSubject":{
                  "id":"eventSubject",
                  "name":"行事曆主旨",
                  "value":"HR APP會議",
                  "type":"string",
                  "format":"n/a"
               },
            }
         ],
         "type":"array",
         "format":"n/a"
      },
      "properties":{
         "format":{
            "n/a":"",
            "YYYYmmdd":"西元年月日",
            "HHmm":"時間時分"
         }
      }
   }
}
```

### HTTP Response when Failed
```json
{
    "status": "fail",
    "code": 500,
    "message": [
        "XXX"
    ],
    "data": {}
}
```

### HTTP Response when Exception
```json
{
    "status": "fail",
    "code": 406,
    "message": [
        "XXX"
    ],
    "data": {}
}
```