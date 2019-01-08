## Wechat Payment

#### Client

1. request generate order in server
2. wait for signatured prepay id
3. generate a button for users to confirm
4. call API using payment information
5. wait for WX request and user enter password
6. (WX send payment authorization)
7. find payment result

#### Server

1. receive request from client
2. call order API 
3. wait for WX to generate prepay
4. send signatured prepay id to client
5. wait for asych notification of payment success

#### SSL and HTTPS and API certificate

- server key and client key ! 
- mutual authentication !
- can ssl be used other than https ?
- what can openSSL do ?
- ways to authenticated API calls : 
  - ssl principles ! 
  - [google example](https://developers.google.com/api-client-library/python/guide/aaa_overview)
  - [client side certificate](https://stackoverflow.com/questions/45233761/ssl-client-authentication-with-python-requests)
  - what is certifi ?
  - [difference between certificate types](https://codebazz.wordpress.com/2017/08/27/difference-between-p12-pfx-vs-crt-cer-vs-pem-vs-der/)
  - explain the mechanism of mutual authentication and single authentication
  - [stackoverflow answer](https://stackoverflow.com/questions/30160108/client-certificates-and-mutual-authentication-in-python?noredirect=1&lq=1)
  - what does a certificate contains ? how it signate?

#### Review of Network Security



#### Questions

1. is XML data the same as python dict?
2. python None and Null
3. python static class
4. python reference and list operations
5. python singleton or util class design pattern.
6. How to place the API certificate in our server?
7. How certificate works
8. How to solve that http bug
9. what is proxy and how is that working
10. what is the relationship between ssl and other .p12 file?
11. 