## Get Countries List

Gets the list of supported countries in Business Catalyst. You are not required to be logged in to use this API.

### Request

* **Method:** GET
* **Server:** https://api-[dub|nj|syd].worldsecuresystems.com/
  * Alternatively, use secure site URI (eg. https://mysite.worldsecuresystems.com)
* **Path:** /api/v2/admin/system/countries

#### Parameters ####

* Query:
	* `ip` - the IP for which you require the appropriate country, or "current" for the current request IP. If not supplied, the entire list of countries supported by Business Catalyst is returned *(string, optional)*

### Response

countryList object with the following properties:

* `items` - an array of country objects which have the following properties:
	* `countryCode`
	* `displayName`

### Examples

Accepts and returns JSON as Content-Type.

#### JSON

**Request:**
~~~
GET https://api.worldsecuresystems.com/api/v2/admin/countries HTTPS/1.1
Connection: keep-alive
Content-Type: application/json
~~~

**Response:**
~~~

HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
 
{
  "currentPage":1,
  "items":
  [
    {
      "countryCode":"AU",
      "displayName":"Australia"
    },
    {
      "countryCode":"US",
      "displayName":"United States"
    },
    ...
  ],
  "itemsPerPageCount":1000,
  "links":
  [
    {
      "rel":"previous",
      "uri":null
    },
    {
      "rel":"next",
      "uri":null
    }
  ],
  "totalItemsCount":240
}
~~~

### Error Codes

This method will return the following error codes:

* `200` - success
* `401`
	* `105000` sub-code - invalid IP passed to "ip" argument
* `500` - internal server error
