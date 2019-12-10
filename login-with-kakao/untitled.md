# Another version



{% api-method method="get" host="https://api.cakes.com" path="/v1/cakes/:id" %}
{% api-method-summary %}
Get Cakes
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" %}
ID of the cake to get, for free of course.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="recipe" type="string" %}
The API will do its best to find a cake matching the provided recipe.
{% endapi-method-parameter %}

{% api-method-parameter name="gluten" type="boolean" %}
Whether the cake should be gluten-free or not.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{    "name": "Cake's name",    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}





#### Step 2: Get an Access Token

After a user has obtained the Authorization code, the user can get Access Token and Refresh Token via the Authorization code in order to call API.

**\[Request\]**

```text
POST /oauth/token HTTP/1.1
Host: kauth.kakao.com
Content-type: application/x-www-form-urlencoded;charset=utf-8
```

You need to include the following query parameters in the authorization URL with POST method.

{% api-method method="post" host="https://kauth.kakao.com/oauth/token" path="" %}
{% api-method-summary %}
Get an Access Token
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-type" type="string" required=true %}
application/x-www-form-urlencoded
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="grant\_type" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

  
 

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Parameters</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
      <th style="text-align:left"><b>Type</b>
      </th>
      <th style="text-align:left"><b>Required</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><em>grant_type</em>
      </td>
      <td style="text-align:left"><code>authorization_code</code> (fixed)</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">O</td>
    </tr>
    <tr>
      <td style="text-align:left"><em>client_id</em>
      </td>
      <td style="text-align:left">
        <p>a REST API key that is issued by Kakao when creating an application.</p>
        <p>You can check this key in [Settings] &gt; [User Management].</p>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">O</td>
    </tr>
    <tr>
      <td style="text-align:left"><em>redirect_uri</em>
      </td>
      <td style="text-align:left">Callback URL that users are redirected to.
        <br /><b>!! This URL must coincide with the designated URL in [Settings]</b> &gt;
        [<b>User Management]</b> &gt; [<b>Login Redirect URI]</b>.</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">O</td>
    </tr>
    <tr>
      <td style="text-align:left"><em>cod</em>e</td>
      <td style="text-align:left">authorization_code that is issued in the [Step 1: Get an Authorization
        code] to get an access token.</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">O</td>
    </tr>
    <tr>
      <td style="text-align:left"><em>client_secret</em>
      </td>
      <td style="text-align:left"><code>client_secret code</code> that is set in [Settings] &gt; [Advanced]
        &gt; [Client Secret]
        <br />ACTIVE &#xC0C1;&#xD0DC; &#xC778; &#xACBD;&#xC6B0; &#xD544;&#xC218;&#xB85C;
        &#xC124;&#xC815;&#xD574;&#xC57C; &#xD568;
        <br />(Required X&#xAC00; &#xC544;&#xB2C8;&#xB77C; &#xD588;&#xB294;&#xB370;
        &#xD574;&#xB2F9; &#xBB38;&#xAD6C;&#xAC00; &#xD63C;&#xB3D9;&#xC744; &#xC90C;.
        ACTIVE&#xAC00; &#xAD6C;&#xCCB4;&#xC801;&#xC73C;&#xB85C; &#xC758;&#xBBF8;&#xD558;&#xB294;
        &#xAC83;&#xC774; &#xBB34;&#xC5C7;&#xC778;&#xC9C0;&#xB3C4; &#xBAA8;&#xD638;)</td>
      <td
      style="text-align:left">String</td>
        <td style="text-align:left">X</td>
    </tr>
  </tbody>
</table>

**\[Example Request\]**

For example, if you request with POST method as follows:

{% tabs %}
{% tab title="Example Request " %}
```text
curl -v -X POST https://kauth.kakao.com/oauth/token \
 -d 'grant_type=authorization_code' \
 -d 'client_id={app_key}' \
 -d 'redirect_uri={redirect_uri}' \
 -d 'code={authorize_code}'
```
{% endtab %}
{% endtabs %}

**\[Example Response\]**

 If successful, which returns the resources in JSON format**.** 

{% tabs %}
{% tab title="Example Response" %}
```text
Content-Type: application/json;charset=UTF-8
{
    "access_token":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "token_type":"bearer",
    "refresh_token":"yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy",
    "expires_in":43199,
    "scope":"Basic_Profile"
}
```
{% endtab %}
{% endtabs %}



**\[Response\]**

The following table lists the parameters in the response body.

| \*\*\*\* |
| :--- |


