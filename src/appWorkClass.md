# appWorkClass
取得當日班別的資訊

### HTTP Request
```
https://114.34.125.246:8090/servlet/HRNative/appWorkPlace
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
| request | {'empid':'admin','date':'20220426'} | Object | 查詢條件

### JSON representation
Here is a JSON representation of request.
```json
{
   "uid":"98599308101484732326",
   "right":"51341911904173543336756162544864820",
   "request":{
      "empid":"admin",
      "date":"20220426"
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
| Key | Value | Type | Description | Required | Format |
|:----------|:-------------|:-----|:------------|:------------|:------------|:------------|
| empid | admin | String | 登入者 | Y | n/a |
| date | 20220426 | String | 查詢日期 | Y | YYYYmmdd |

### HTTP Response when Successful
```json
{
    "status": "success",
    "message": [
        "回傳成功"
    ],
    "data": {
        "properties": {
            "format": {
                "HHmm": "時間時分",
                "YYYYmmdd": "西元年月日"
            }
        },
        "class": {
            "name": "班別資訊",
            "type": "object",
            "value": {
                "workOff": {
                    "name": "下班時間",
                    "type": "object",
                    "value": "1730",
                    "format": "HHmm",
                    "id": "workOff"
                },
                "workOn": {
                    "name": "上班時間",
                    "type": "object",
                    "value": "0830",
                    "format": "HHmm",
                    "id": "workOn"
                },
                "workClassName": {
                    "name": "班別名稱",
                    "type": "object",
                    "value": "通用班(8-17)",
                    "format": "n/a",
                    "id": "workClassName"
                },
                "workDate": {
                    "name": "班別日期",
                    "type": "object",
                    "value": "20220426",
                    "format": "n/a",
                    "id": "workDate"
                },
                "workClass": {
                    "name": "班別代號",
                    "type": "object",
                    "value": "01",
                    "format": "n/a",
                    "id": "workClass"
                }
            },
            "format": "n/a",
            "id": "class"
        }
    }
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
