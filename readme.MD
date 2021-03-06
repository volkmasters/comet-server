![CppComet](https://comet-server.com/img/CppComet.png)

Comet technology – allows sending arbitrary messages to client through server initiative

## How it works

* Browser opens page of your site.
* After loading this page JavaScript Api establishes a persistent connection to CppComet using websockets.
* While page is open, your server can send text message to client. It appeals via [CometQL API](http://comet-server.org/doku.php/en:comet:cometql) to CppComet and transfer message for browser.
* CppComet uses open connection with browser for delivers message in to JavaScript api in browser.
* [JavaScript API](http://comet-server.org/doku.php/en:comet:javascript_api) delivers this message to your callback.

# Features

* Api for more then 9 languages. [CometQL API](http://comet-server.org/doku.php/en:comet:cometql) allows you connect to server by mysql protocol.
* Good documentation in [Russian](http://comet-server.org/doku.php/ru) and [English](http://comet-server.org/doku.php/en) languages
* Allow sending a private message to users
* Supports users authenticating on the server
* Allows you to send public messages to users via channels
 
# Demo
 
* https://github.com/CppComet/php-chat-example
* https://github.com/CppComet/comet-server/tree/master/demo/simple-chat
* https://github.com/CppComet/auth-example

## Demo access to server API

For demo access use credentials:
```
Login: 15
Password:lPXBFPqNg3f661JcegBY0N0dPXqUBdHXqj2cHf04PZgLHxT6z55e20ozojvMRvB8
Host: app.comet-server.ru
```

CppComet has cloud saas alternative that can be used for testing and demo access.
In the following examples I will use demonstration access from [comet-server.com](http://comet-server.com) for those who could not or were too lazy to deploy the server on their vps.

Example of connecting to [cometQL api](http://comet-server.org/doku.php/en:comet:cometql) from console using mysql-client:
```
mysql -h app.comet-server.ru -u15 -plPXBFPqNg3f661JcegBY0N0dPXqUBdHXqj2cHf04PZgLHxT6z55e20ozojvMRvB8 -DCometQL_v1 --skip-ssl
```
## Simple chat demo

[Simple chat demo page](http://comet-server.com/doc/CometQL/MainPageChat/index.php)
![Simple chat demo gif](https://comet-server.com/doc/CometQL/CometQL-demo.gif)

On this gif animation you see how send message to [web chat](http://comet-server.com/doc/CometQL/MainPageChat/index.php) from CppComet api.

We connect to CppComet by mysql protocol and send [CometQL query](http://comet-server.org/doku.php/en:comet:cometql).

For connect to demo server use this command:
```
mysql -h app.comet-server.ru -u15 -plPXBFPqNg3f661JcegBY0N0dPXqUBdHXqj2cHf04PZgLHxT6z55e20ozojvMRvB8 -DCometQL_v1 --skip-ssl
```
For send message to demo chat use this query:
```
INSERT INTO pipes_messages (name, event, message)VALUES("web_MainPageChat", "", '{ "text":"My text","name":"My name"}' );
```

# Documentation and examples

Comet server is written in C++, for storing data using MySQL.   

[Documentation and examples](http://comet-server.org/)
  
### Building from source and launch

How to build and run [EN](http://comet-server.org/doku.php/en:comet:building-from-source) or [RU](http://comet-server.org/doku.php/comet:building-from-source)
  
### CometQL API: 

CometQL API documentation [EN](http://comet-server.org/doku.php/en:comet:cometql) or [RU](http://comet-server.org/doku.php/comet:cometql)

 - To connect to the comet server api from any server-side language is used CometQL [EN](http://comet-server.org/doku.php/en:comet:cometql) or [RU](http://comet-server.org/doku.php/comet:cometql)
 
### JavaScript API: 

JavaScript API documentation [EN](http://comet-server.org/doku.php/en:comet:javascript_api) or [RU](http://comet-server.org/doku.php/comet:javascript_api)

- To connect to the server from JavaScript API use file from api/CometServerApi.js

License
----

GNU AGPLv3

 
