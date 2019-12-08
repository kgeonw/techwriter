---
description: Kakao API Portal (English ver.)
---

# LOGIN WITH KAKAO

Kakao: Supplier

You: a third-party application

User: users

## **Overview**

Kakao Login API enables users to log in your application with their kakao accounts in a fast, simple, and secure way. With the easy-to use functions, users do not need to sign up or log in a third application. Users do not need to sign up or log in a third application with the easy-to use functions, which helps you to keep users on your application and maximize the number of people using your application.



Table of Contents

* Login Flow
* 




## **Login Flow** 

**\(Or Conceptual Overview\)**

Kakao Login API complies with OAuth 2.0. The Open Authorization\(OAuth\) is a standard authorization framework that allows a third-party application to access limited information with an access token without user’s ID and password. Here is the process of OAuth authentication.

1. A User clicks the \[Login with Kakao\] button.

2. Once the user logs in with the user’s Kakao ID and password, the user is redirected to a screen that asks Users’ consent to access the limited information. //to request a request token. //

3. Once the user approves permissions, the Kakao authorization server validates the user’s credentials and issues Authorization Code. The user is redirected to your app through `redirect_uri` with the Authorization Code.

4. Once your application validates the Authorization code, your app requests Access Token and Refresh Token.

5. The Kakao authorization server validates and issues Access Token and Refresh Token based on the Authorization code.

Kakao redirects the user back to your app thorugh/via Redirect URI  
****

## **Before you begin**

### **1.**     **Create an app**

'시작하기 &gt; [앱 생성](https://developers.kakao.com/docs/restapi/getting-started#앱-생성)' 항목

### **2.**     **Configure an app**

'시작하기 &gt; [사용자 관리 설정](https://developers.kakao.com/docs/restapi/getting-started#사용자-관리-설정)' 항목 



#### Step1: Activate \[Login with Kakao\]

![](.gitbook/assets/image%20%289%29.png)

#### Step2: Specify Items for Permissions 

![](.gitbook/assets/image%20%281%29.png)

#### Step3: Set redirect URL

![](.gitbook/assets/image%20%2837%29.png)

#### Step4: Add Kakaotalk Channel



#### Step5: Disconnect an app

## Integrating Kakao Login

### Authentication

Kakao Login API complies with OAuth 2.0. The Open Authorization\(OAuth\) is a standard authorization framework that allows a third-party application to access limited information with an access token without user’s ID and password. For the details about OAuth 2.0, click [here](https://tools.ietf.org/html/rfc6749).

#### 

> **Table of Contents**
>
>  Step1: Get an Authorization code
>
>  Step2: Get an Access Token
>
>  Step3: Refresh an Access Token
>
>  Step4: Validate an Access Token & Get Information

#### 

#### Step1: Get an Authorization code



#### Step2: Get an Access Token

After a user has obtained the Authorization code, the user can get Access Token and Refresh Token via the Authorization code in order to call API.

**\[Request\]**

```text
POST /oauth/token HTTP/1.1
Host: kauth.kakao.com
Content-type: application/x-www-form-urlencoded;charset=utf-8
```

{% api-method method="post" host="https://kauth.kakao.com/oauth/token" path="" %}
{% api-method-summary %}
 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="grant\_type" type="string" required=true %}
`authorization_code` \(fixed\)
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The following is an example of Response in JSON format.
{% endapi-method-response-example-description %}

```
Content-Type: application/json;charset=UTF-8
{
    "access_token":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "token_type":"bearer",
    "refresh_token":"yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy",
    "expires_in":43199,
    "scope":"Basic_Profile"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=302 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Add more examples...
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=304 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Add more examples...
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Include the following query parameters in the URL with POST method.  
 아래 파라미터의 값들을 POST로 요청합니다.

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
      <td style="text-align:left"><em>authorization_code</em> (fixed)</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">O</td>
    </tr>
    <tr>
      <td style="text-align:left"><em>client_id</em>
      </td>
      <td style="text-align:left">
        <p>a REST API key that is issued by Kakao when creating an application.</p>
        <p>You can check this key in Setting &gt; User Management.</p>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">O</td>
    </tr>
    <tr>
      <td style="text-align:left"><em>redirect_uri</em>
      </td>
      <td style="text-align:left">Callback URL that users are redirected to.
        <br /> <b>This URL must coincide with the designated URL in Settings</b> &gt; <b>User Management</b> &gt; <b>Login Redirect URI</b>.</td>
      <td
      style="text-align:left">String</td>
        <td style="text-align:left">O</td>
    </tr>
    <tr>
      <td style="text-align:left"><em>cod</em>e</td>
      <td style="text-align:left">authorization_code that is issued in the [Step1: Getn an Authorization
        code] to get an access token.</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">O</td>
    </tr>
    <tr>
      <td style="text-align:left"><em>client_secret</em>
      </td>
      <td style="text-align:left">client_secret code that is set in <b>Settings</b> &gt; <b>Advanced</b> &gt; <b>Client Secret</b>
        <br
        />ACTIVE &#xC0C1;&#xD0DC; &#xC778; &#xACBD;&#xC6B0; &#xD544;&#xC218;&#xB85C;
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
</table> **\[Example Request\]**

The following is an example of Request**.**

```text
curl -v -X POST https://kauth.kakao.com/oauth/token \
 -d 'grant_type=authorization_code' \
 -d 'client_id={app_key}' \
 -d 'redirect_uri={redirect_uri}' \
 -d 'code={authorize_code}'
```

**\[Response\]**

The following is an example of Response in JSON format.

**HTTP/1.1** **200** **OK**

Content-Type: application/json;charset=UTF-8

{

    "access\_token":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",

    "token\_type":"bearer",

    "refresh\_token":"yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy",

    "expires\_in":43199,

    "scope":"Basic\_Profile"

}

| **Property** | **Description** | **Type** |
| :--- | :--- | :--- |
| access\_token | A token used to call API | String |
| Token\_type | Bearer | String |
| refresh\_token | A token used to get a new access tone | String |
| expire\_in | Amount of time in seconds until the access token expires | Integer |
| Scope | Permission to granted by the user | String |

#### 

#### Step3: Refresh an Access Token

사용자 토큰 갱신하기 



#### Step4: Validate an Access Token & Get Information

사용자 토큰 유효성 검사 및 정보 얻기

### 

### Add a Login Button

로그인 API를 사용한 후, [\[카카오 로그인\] 버튼](https://developers.kakao.com/buttons#Login_Buttons)을 추가하는 방법을 이 항목으로 추가.  
순차적으로 진행하는 방식으로 배치 변경



#### Button Download

![](.gitbook/assets/image%20%2850%29.png)

#### 

#### Design guidelines

일관된 디자인의 버튼 제공을 위하여 버튼 디자인 가이드라인 항목 추가



#### Best Practices

\[카카오 로그인\] 버튼을 효과적으로 사용할 수 있는 방법**\(Tip\)**과 예시 추

  


## After Login

**\(Or User Management/ Advanced\)**

\*\*\*\*

### Log out of Kakao

'로그아웃' 항목

### Disconnect an app

'연동 해제' 항목

### Save User Profile

'사용자 정보 저장' 항목

### Retrieve user profile 

'사용자 정보 요청' 항목

### Retrieve User **ID** List  

'사용자 ID 리스트 요청' 항목

### Make an additional request 

'동적동의' 항목

### 

### \*\*\*\*

## **Release Note**

'v1 사용자 정보 요청과 달라진 점'을 Release Note로 이동

변경 이력을 표로 정리 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Version</th>
      <th style="text-align:left">Release Date</th>
      <th style="text-align:left">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>v2</p>
        <p>(current)</p>
      </td>
      <td style="text-align:left">yyyymmdd</td>
      <td style="text-align:left">
        <ul>
          <li>&#xD2B9;&#xC815; property&#xB9CC; &#xAC00;&#xC9C0;&#xACE0; &#xAC00;&#xACE0;
            &#xC2F6;&#xC744;&#xB54C; &#xC0AC;&#xC6A9;&#xD558;&#xB294; &#xD30C;&#xB77C;&#xBBF8;&#xD130;
            &#xC774;&#xB984;&#xC774; &#xBCC0;&#xACBD;&#xB418;&#xC5C8;&#xC2B5;&#xB2C8;&#xB2E4;.
            propertyKeys -&gt; property_keys</li>
          <li>response&#xC758; &#xD0A4; &#xC911; kaccount prefix&#xB97C; &#xAC00;&#xC9C4;
            &#xD0A4;&#xB294; kakao_account &#xD558;&#xC704;&#xB85C; &#xACC4;&#xCE35;&#xC774;
            &#xC0DD;&#xACBC;&#xC2B5;&#xB2C8;&#xB2E4;.</li>
          <li>&#xCE74;&#xCE74;&#xC624;&#xACC4;&#xC815;&#xC815;&#xBCF4;&#xC778; &#xD504;&#xB85C;&#xD544;,
            &#xC5F0;&#xB839;&#xB300;, &#xC0DD;&#xC77C;, &#xC131;&#xBCC4; &#xAC12;&#xC774;
            &#xCD94;&#xAC00; &#xB418;&#xC5C8;&#xC2B5;&#xB2C8;&#xB2E4;.</li>
          <li>&#xCD94;&#xAC00; &#xB3D9;&#xC758;&#xAC00; &#xD544;&#xC694;&#xD55C; &#xD504;&#xB85C;&#xD544;,
            &#xC774;&#xBA54;&#xC77C;, &#xC5F0;&#xB839;&#xB300;, &#xC0DD;&#xC77C;, &#xC131;&#xBCC4;&#xC758;
            &#xACBD;&#xC6B0; XXX_needs_agreement &#xC751;&#xB2F5;&#xC774; &#xCD94;&#xAC00;
            &#xB418;&#xC5C8;&#xC2B5;&#xB2C8;&#xB2E4;.</li>
          <li>response&#xC758; &#xAC12;&#xC774; &#xC874;&#xC7AC;&#xD558;&#xC9C0; &#xC54A;&#xC73C;&#xBA74;,
            &#xD0A4;&#xB3C4; &#xB0B4;&#xB824;&#xAC00;&#xC9C0; &#xC54A;&#xC2B5;&#xB2C8;&#xB2E4;.</li>
          <li>&#xC11C;&#xBC84;&#xAC00; &#xBD88;&#xC548;&#xC815;&#xD55C; &#xACBD;&#xC6B0;,
            kakao_account &#xD558;&#xC704;&#xC758; &#xAC12;&#xC744; &#xAC00;&#xC9C0;&#xACE0;
            &#xC624;&#xC9C0; &#xBABB;&#xD558;&#xB354;&#xB77C;&#xB3C4; &#xC5D0;&#xB7EC;&#xB97C;
            &#xBC1C;&#xC0DD;&#xC2DC;&#xD0A4;&#xC9C0; &#xC54A;&#xC2B5;&#xB2C8;&#xB2E4;.
            &#xAF2D; &#xD544;&#xC694;&#xD55C; &#xACBD;&#xC6B0;&#xB294; &#xC7AC;&#xC694;&#xCCAD;&#xC744;
            &#xD558;&#xC154;&#xC57C; &#xD569;&#xB2C8;&#xB2E4;.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">v1</td>
      <td style="text-align:left">yyyymmdd</td>
      <td style="text-align:left">
        <ul>
          <li>&#xC0C8; REST API &#xAC1C;&#xBC1C;&#xAC00;&#xC774;&#xB4DC; &#xC0DD;&#xC131;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## Glossary

개발가이드에 나오는 용어를 정리한 용어집\(Glossary\) 항목 새로 추가 





\*\*\*\*

{% hint style="info" %}
**Is this page helpful?**

 **Yes / Kind of / No**
{% endhint %}

\*\*\*\*

 **&gt;&gt; Next steps:** Kakao Talk

