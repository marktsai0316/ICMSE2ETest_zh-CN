# <a name="update-rangeformat"></a>更新 rangeformat

更新 rangeformat 对象的属性。
## <a name="prerequisites"></a>先决条件
要执行此 API 需要以下**范围**︰ 
## <a name="http-request"></a>HTTP 请求
<!-- { "blockType": "ignored" } -->
```http
PATCH /workbook/names(<name>)/range/format
PATCH /workbook/worksheets(<id|name>)/range(<address>)/format
PATCH /workbook/tables(<id|name>)/columns(<id|name>)/range/format
```
## <a name="optional-request-headers"></a>可选的请求标头
| 名称       | 说明|
|:-----------|:-----------|
| 授权  | 持有者<code>|


## <a name="request-body"></a>请求正文
在请求正文中，提供相关应更新的字段的值。 不包括在请求正文中的现有属性将保留其以前的值或重新计算基于的更改其他属性值。 为了获得最佳性能不应包括尚未更改的现有值。

| 属性     | 类型   |说明|
|:---------------|:--------|:----------|
|列宽|double|获取或设置范围内的所有列的宽度。 如果列宽不是统一的则将返回 null。|
|horizontalAlignment|string|代表指定对象的水平对齐方式。 Possible values are: `General`, `Left`, `Center`, `Right`, `Fill`, `Justify`, `CenterAcrossSelection`, `Distributed`.|
|rowHeight|double|获取或设置区域中所有行的高度。 如果将行高不统一将返回 null。|
|verticalAlignment|string|代表指定对象的垂直对齐方式。 可能的值为︰ `Top`， `Center`， `Bottom`， `Justify`， `Distributed`。|
|文字环绕|布尔|指示是否 Excel 会将文本包装对象中。 Null 值表示的整个区域不具有统一换行设置|

## <a name="response"></a>响应
如果成功，此方法返回`200 OK`响应代码和更新后的[RangeFormat](../resources/rangeformat.md)对象在响应正文中。
## <a name="example"></a>示例
##### <a name="request"></a>请求
下面是示例请求。
<!-- {
  "blockType": "request",
  "name": "update_rangeformat"
}-->
```http
PATCH https://graph.microsoft.com/v1.0/me/drive/items/<id>/workbook/names(<name>)/range/format
Content-type: application/json
Content-length: 96

{
  "columnWidth": 99,
  "horizontalAlignment": "horizontalAlignment-value",
  "rowHeight": 99
}
```
##### <a name="response"></a>响应
这里是响应的示例。 注意︰ 为了简单起见，此处所示的响应对象可能被截断。 从实际调用将返回的所有属性。
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.rangeFormat"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 96

{
  "columnWidth": 99,
  "horizontalAlignment": "horizontalAlignment-value",
  "rowHeight": 99
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update rangeformat",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->