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
    	will return error message 
    	{
    	'result': 'error', 
    	'message': "INVALID_REFRESH_TOKEN" ,
    	}
    	if need client to get authcode
    """
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
st1=>start: Client
op1=>operation: Click and Check openId
cond1=>condition: Has open_id ?
op2=>operation: send openId to server
end1=>end: get authcode and send
cond2=>condition: token expired?
end3=>end: complete
op4=>operation: receive if expired from server
end2=>end: get authcode and send

st1->op1->cond1
cond1(no)->end1
cond1(yes)->op2->op4->cond2
cond2(no)->end3
cond2(yes)->end2

```

```flow
st=>start: server
op1=>operation: find refresh token
op2=>operation: get userinfo
op3=>operation: normal login, regain refresh token
op4=>operation: register user, get refresh token
op5=>operation: need authcode from client
op6=>operation: refresh refresh token
cond1=>condition: open_id none?
cond2=>condition: does user exist?
cond3=>condition: refresh token expired?

st->cond1
cond1(yes)->op2->cond2
cond1(no)->op1->cond3
cond2(yes)->op3
cond2(no)->op4
cond3(yes)->op5
cond3(no)->op6

```

