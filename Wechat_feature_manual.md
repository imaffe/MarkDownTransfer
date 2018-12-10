## Patch Manual For Wechat plugin

#### 1. kfsClientService.py

File under dir **kfsLib/kfsService/kfsWebService/** .  Add a new function **kfsWechatRegisterCL**

```python
class kfsWechatRegisterAndLoginCL(kfsView):
    @responseNorm
    def post(self, request):
        """
        Args :
            openId : the encryted wechat user id for a specific Wechat public 							application
            authCode : the authCode from wxapi used to get access_token
        """
        openId = request.POST.get('openId')
        authCode = request.POST.get('authCode')
        device = request.POST.get('device')
        clientVersion = request.POST.get('clientVersion')
        response = self.serviceHandler('wechatRegisterAndLoginCL',  openId, authCode, 									      device, clientVersion)
        return response
```

****

#### 2. kfsUserService.py

File under dir **kfs/kfsLib/kfsService/**. And this is the function that really does something !  **

```python
def wechatRegisterAndLoginCL(self, openId, authCode, device, clientVersion):
    """
    Description : 
    	
    """
```

```python
def wechatRegisterCL(self, ):
```

#### 3.kfsWechat.py

File under dir **kfsLib/kfsCore/**

- **refreshAccessToken**(refreshToken) :  get a response containing  a new access token and a new refresh token and OpenId
- **getWXApiResponse**(authCode) : use auth code to get an initial access token and refresh token and openId
- **getUserInfo**(openId, accessToken) : use openId and access token to get some basic information of the user

#### 4. urls.py

```
# added a new line
...
url(r'^client/wxregisterandlogin/', kfsWechatRegisterAndLoginCL.as_view()),
...
```

#### 5. Data Flow

```flow
flow
client=>start: Client
openidCheck=>operation: Click and Check openId
cond_openidCheck=>condition: Has open_id ?
sendopenId=>operation: send openId to server
getAuthCode=>end: get authcode from weixin and send
cond_expireCheck=>condition:refresh token expired?

client->openidCheck->cond_openidCheck
cond_openidCheck(yes)->sendopenId
cond_openidCheck(no)->getAuthCode

```