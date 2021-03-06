# <a name="delete-permission"></a>删除权限

删除权限。 可以删除只不可继承的权限。 **InheritedFrom**属性必须为空。 应用程序只能删除他们所创建的权限。


## <a name="prerequisites"></a>先决条件
以下**范围**之一是执行此 API 所需的︰

  * Files.ReadWrite

## <a name="http-request"></a>HTTP 请求

<!-- { "blockType": "ignored" } -->
```http
DELETE /me/drive/root/permissions/<id>
DELETE /me/drive/items/<id>/permissions/<id>
```

## <a name="request-headers"></a>请求标头

| 名称          | 类型   | 说明                                                                                                                                                                                       |
|:--------------|:-------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 授权 | string | 持有者<token>。 必需。                                                                                                                                                                         |
| 如果匹配      | string | 如果此请求标头将包括提供 eTag （或 cTag） 与当前标记的项目，不匹配`412 Precondition Failed`返回的响应并不会删除该项目。 |

## <a name="request-body"></a>请求正文
请不要提供此方法请求正文。

## <a name="response"></a>响应
如果成功，此方法返回`204, No Content`响应代码。 它不返回任何响应正文中。

## <a name="example"></a>示例

##### <a name="request"></a>请求

下面是示例请求。

<!-- {
  "blockType": "request",
  "name": "delete_permission"
}-->
```http
DELETE /me/drive/root/permissions/<id>
```

##### <a name="response"></a>响应

这里是响应的示例。

<!-- {
  "blockType": "response",
  "truncated": false
} -->
```http
HTTP/1.1 204 No Content
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Delete permission",
  "keywords": "",
  "section": "documentation",
  "tocPath": "OneDrive/Item/Delete permission"
}-->
