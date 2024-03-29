## Get Web App Item Categories

Get a list of all the categories for a webapp item.

**Note:** This operation does not support: pagination, filtering, or sorting parameters.

### Request

* **Method:** GET
* **Server:** https://api-[dub|nj|syd].worldsecuresystems.com
  * Alternatively, use secure site URI (eg. https://mysite.worldsecuresystems.com)
* **Path:** /api/v2/admin/sites/[siteId]/webapps/[webappName]/items/[itemID]/categories
  * Alternatively, use "current" instead of [siteId]
* **Auth Header:** Site token required
* **Required Permissions:** View Web App Items

### Response

Returns a paginator object with items array of integers (category ids).


### Examples

Accepts and returns JSON as Content-Type.

#### JSON

**Request:**
~~~
GET /api/v2/admin/sites/325435/webapps/Cars/items/454365/categories HTTPS/1.1
Authorization: 14f87f21c5ea4830a06a6314a8aad82b45bc61dc08f24a0fb55599cea83ca811
Connection: keep-alive
Content-Type: application/json
~~~

**Response:**

~~~

HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Content-Encoding: gzip
Vary: Accept-Encoding
Server: Microsoft-IIS/7.5
Access-Control-Allow-Origin: *
Access-Control-Allow-Headers: Authorization, Accept-Language, Content-Type
Access-Control-Allow-Methods: GET, HEAD, POST, PUT, DELETE
Access-Control-Expose-Headers: Location
Access-Control-Max-Age: 99999
Content-Length: length
 
{
  "totalItemsCount": 3,
  "skip": 0,
  "limit": 100,
  "links": [
      {
        "rel":"self",
        "uri":"https:\/\/bc-local.worldsecuresystems.com\/api\/v2\/admin\/sites\/325435\/webapps\/Cars\/items\/454365\/categories"
      },
      {
        "rel":"categories",
        "uri":"https:\/\/bc-local.worldsecuresystems.com\/api\/v2\/admin\/sites\/325435\/categories"
      },
      {
        "rel":"category",
        "uri":"https:\/\/bc-local.worldsecuresystems.com\/api\/v2\/admin\/sites\/325435\/categories/{categoryId}"
      }
  ],
  "items": [45345,45346,45400]
}
~~~

### Error Codes

This method will return the following error codes:

* `200` - success
* `400` - bad request
  * `200000` - An unspecified error has occured
* ``401` - unauthorized - when the Authorization header is not present, or contains an invalid site token
* `403` - forbidden - when the user does not have View WebApp Item Permission
* `404` - not found:
	* `190001` - The web app could not be found (the webAppName param from the URL does not match)
	* `200001` - The webapp item was not found (the webAppName and webAppItemId from the URL do not match)
