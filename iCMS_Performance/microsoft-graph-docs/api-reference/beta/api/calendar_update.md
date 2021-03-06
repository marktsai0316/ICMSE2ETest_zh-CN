# <a name="update-calendar"></a>更新日历

更新日历对象的属性。
## <a name="prerequisites"></a>先决条件
需执行此 API 之一以下**范围**︰ *Calendars.ReadWrite*
## <a name="http-request"></a>HTTP 请求
<!-- { "blockType": "ignored" } -->
用户或组的默认[日历](../resources/calendar.md)。
```http
PATCH /me/calendar
PATCH /users/<id | userPrincipalName>/calendar
PATCH /groups/<id>/calendar
```
[日历](../resources/calendar.md)的用户的默认值[calendarGroup](../resources/calendargroup.md)。
```http
PATCH /me/calendars/<id>
PATCH /users/<id | userPrincipalName>/calendars/<id>

PATCH /me/calendarGroup/calendars/<id>
PATCH /users/<id | userPrincipalName>/calendarGroup/calendars/<id>
```
在特定的[calendarGroup](../resources/calendargroup.md)的用户的[日历](../resources/calendar.md)。
```http
PATCH /me/calendarGroups/<id>/calendars/<id>
PATCH /users/<id | userPrincipalName>/calendarGroups/<id>/calendars/<id>
```
## <a name="request-headers"></a>请求标头
| 页眉       | 值 |
|:---------------|:--------|
| 授权  | 持有者<token>。 必需。  |
| 内容类型  | 应用程序/json。 必需。  |

## <a name="request-body"></a>请求正文
在请求正文中，提供相关应更新的字段的值。 不包括在请求正文中的现有属性将保留其以前的值或重新计算基于的更改其他属性值。 为了获得最佳性能不应包括尚未更改的现有值。

| 属性     | 类型   |说明|
|:---------------|:--------|:----------|
|color|String|指定要区分从用户界面中的其他日历的日历的颜色主题。 属性值是︰ LightBlue = 0，LightGreen = 1，LightOrange = 2，LightGray = 3，LightYellow = 4，LightTeal = 5，LightPink = 6，LightBrown = 7，LightRed = 8，MaxColor = 9，自动 = 1|
|isDefaultCalendar|Boolean|如果此属性为 true 的日历在用户的默认日历，假的其他方面。|
|name|String|日历名称。|

## <a name="response"></a>响应
如果成功，此方法返回`200 OK`响应代码和更新的[日历](../resources/calendar.md)对象在响应正文中。
## <a name="example"></a>示例
##### <a name="request"></a>请求
下面是示例请求。
<!-- {
  "blockType": "request",
  "name": "update_calendar"
}-->
```http
PATCH https://graph.microsoft.com/beta/me/calendar
Content-type: application/json
Content-length: 48

{
  "name": "name-value",
  "color": {
  }
}
```
##### <a name="response"></a>响应
这里是响应的示例。 注意︰ 为了简单起见，此处所示的响应对象可能被截断。 从实际调用将返回的所有属性。
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.calendar"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 98

{
  "name": "name-value",
  "color": {
  },
  "isDefaultCalendar": false,
  "changeKey": "changeKey-value",
  "id": "id-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update calendar",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
