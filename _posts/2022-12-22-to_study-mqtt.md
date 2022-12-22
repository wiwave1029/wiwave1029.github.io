---
#typora-root-url:  ../
layout: single
title: "How to study MQTT ?"
categories: [mqtt]
tag: [mqtt]
toc: true
author_profile: true
---

<http://www.steves-internet-guide.com/mqtt-basics-course/>

## Steves님의 자습서 기준으로 정리

초보자를 위한 MQTT 자습서 및 과정
이것은 과정으로 정리된 자습서 모음이며 MQTT 프로토콜의 기초와 IOT 프로젝트에서 
사용하는 방법을 이해하고자 하는 완전한 초보자를 위한 것입니다.

이 과정은 MQTT 프로토콜의 기본 사항과 중요한 기능을 안내하는 일련의 자습서, 
비디오 및 예제로 구성됩니다.

과정이 끝나면 MQTT와 가장 중요한 기능을 잘 이해하게 될 것입니다.

많은 자습서에는 Python으로 작성된 예제가 포함되어 있지만 프로그래밍이 필요하지 않습니다. 
그러나 많은 예제에 대한 데모 스크립트를 다운로드할 수 있습니다.

## MQTT 기초
### MQTT 작동 방식 
<http://www.steves-internet-guide.com/mqtt-works/>    

이 자습서에서는 MQTT에서 사용하는 게시 및 구독 모델과 ​​http에서 사용하는 
클라이언트 서버 모델에 비해 이점을 살펴봅니다.

### MQTT 토픽 및 토픽 구조 이해
<http://www.steves-internet-guide.com/understanding-mqtt-topics/>  
 MQTT 클라이언트는 이메일과 같은 서비스에서 익숙한 주소가 없지만 
주제를 사용하여 메시지를 공유합니다.

### MQTT 게시, 구독 및 메시지 교환
<http://www.steves-internet-guide.com/mqtt-publish-subscribe/>   
 MQTT 클라이언트 간에 메시지가 교환되는 방법을 다룹니다.

## 인증 메커니즘
MQTT는 다양한 인증 및 데이터 보안 메커니즘을 지원합니다.
이러한 보안 메커니즘은 MQTT 브로커에서 구성되며 해당 메커니즘을 준수하는 것은 클라이언트의 책임입니다.  

<http://www.steves-internet-guide.com/mqtt-security-mechanisms/>    

MQTT 보안 메커니즘 소개를 참조하십시오 .

## 웹소켓

<http://www.steves-internet-guide.com/mqtt-websockets/>  

Websocket 을 사용하면 MQTT 데이터를 웹 브라우저로 직접 수신할 수 있습니다.
이는 웹 브라우저가 MQTT 데이터를 표시하기 위한 사실상의 인터페이스가 될 수 있으므로 중요합니다.
웹 브라우저에 대한 MQTT 웹 소켓 지원은 Javascript MQTT 클라이언트 에서 제공 합니다.
Using MQTT Over WebSockets  자습서 는 자세한 내용을 다루고 예제 스크립트를 포함합니다.




## MQTT v3.1 Features
사용 방법을 알고 이해해야 하는 몇 가지 중요한 Features가 있습니다. 이 자습서에서는 이러한 Features를
자세히 살펴보고 사용 예를 포함합니다.

-Clean Sessions and Persistent Connections(클린 세션 및 영구 연결)
-Retained Messages(보존된 메시지)
-Last Will and Testament(유언장)
-Keep Alives
-QOS (Quality of Service)(서비스 품질)  
<http://www.steves-internet-guide.com/mqtt-basics-course/>  


### 클린 세션 및 영구 연결
클라이언트가 브로커에 연결할 때 다음 중 하나를 사용하여 연결할 수 있습니다.
비 영구 연결 (깨끗한 세션) 또는 지속적인 연결 ..
비영구 연결 을 사용 하면 브로커는 클라이언트에 대한 구독 정보나 배달되지 않은 메시지를 저장하지 않습니다 .
이 모드는 클라이언트가 메시지를 게시할 때만 이상적입니다.

영구 연결 을 사용하여 내구성 있는 클라이언트 로 연결할 수도 있습니다 .
이 모드에서 브로커/서버는 게시된 메시지 및 구독 클라이언트의 QOS에 따라 연결이 끊어진 경우 클라이언트에 대한 메시지를 저장합니다.

지속적인 연결 이해 - Python 예제 자습서 는 Python을 사용하는 다양한 옵션을 보여주고 
샘플 코드를 포함합니다.

### 보존된 메시지
앞서 메시지 게시에 대해 이야기할 때 보존된 메시지에 대해 언급했습니다.

일반적으로 게시자가 주제에 메시지를 게시하고 아무도 해당 주제를 구독하지 않는 경우 메시지는 단순히 브로커에 의해 삭제 됩니다.

그러나 게시자는 보유 메시지 플래그 를 설정하여 해당 주제에 대한 마지막 메시지를 보관하도록 브로커에게 알릴 수 있습니다 .

예를 들어 센서가 긴 시간 간격으로 상태를 게시하는 경우에 매우 유용할 수 있습니다.

MQTT Retained Messages Explained 튜토리얼에서는 Python을 사용 하는 예제를 통해 이를 자세히 다룹니다.

### 유언장
마지막 유언장 메시지는 게시자의 예기치 않은 종료를 구독자에게 알리는 데 사용됩니다.

각 주제 에는 브로커에 저장된 마지막 유언장 메시지가 있을 수 있습니다.

마지막 유언장 -

자습서는 마지막 유언장을 설정하고 트리거하는 과정을 안내합니다.

### 킵얼라이브
MQTT는 언제든지 데이터를 보내고 받을 수 있도록 일반적으로 클라이언트가 열어 놓은 TCP/IP 연결을 사용합니다.
특정 시간 동안 열린 연결을 통해 데이터가 흐르지 않으면 클라이언트는 PINGREQ를 생성 하고 브로커로부터 PINGRESP 를 받을 것으로 예상합니다 .
이것이 실패하면 서버는 연결이 끊어진 것으로 간주하고 닫습니다. MQTT 연결 유지 자습서에서는 
이 프로세스를 예제와 함께 다룹니다.


<http://www.steves-internet-guide.com/mqtt-clean-sessions-example/>  
<http://www.steves-internet-guide.com/mqtt-retained-messages-example/>  
<http://www.steves-internet-guide.com/mqtt-last-will-example/>  
<http://www.steves-internet-guide.com/mqtt-keep-alive-by-example/>  
<http://www.steves-internet-guide.com/mqtt-python-beginners-course/>  

