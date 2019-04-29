---
title: IXPLogon IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon
api_type:
- COM
ms.assetid: 4d24ecaf-11d0-4362-8207-be3407736d7b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 46f4e3fc8f554f332ab9b1d8a6cb33e9e21dd9a5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432532"
---
# <a name="ixplogon--iunknown"></a>IXPLogon : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为 MAPI 后台处理程序提供对传输提供程序的访问权限。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|公开者:  <br/> |传输登录对象  <br/> |
|实现者：  <br/> |传输提供程序  <br/> |
|调用者：  <br/> |MAPI 后台处理程序  <br/> |
|接口标识符:  <br/> |IID_IXPLogon  <br/> |
|指针类型:  <br/> |LXPLOGON  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[AddressTypes](ixplogon-addresstypes.md) <br/> |返回传输提供程序处理的收件人的类型。  <br/> |
|**RegisterOptions** <br/> | *不支持或记录。*  <br/> |
|[TransportNotify](ixplogon-transportnotify.md) <br/> |指示发生了传输提供程序请求通知的事件。  <br/> |
|[待机](ixplogon-idle.md) <br/> |指示系统处于空闲状态, 使传输提供程序能够执行低优先级操作。  <br/> |
|[TransportLogoff](ixplogon-transportlogoff.md) <br/> |启动注销过程。  <br/> |
|[SubmitMessage](ixplogon-submitmessage.md) <br/> |指示 MAPI 后台处理程序有要传递的传输提供程序的消息。  <br/> |
|[EndMessage](ixplogon-endmessage.md) <br/> |通知传输提供程序 MAPI 后台处理程序已完成对出站邮件的处理。  <br/> |
|[轮询](ixplogon-poll.md) <br/> |指示传输提供程序是否已收到一个或多个入站邮件。  <br/> |
|[StartMessage](ixplogon-startmessage.md) <br/> |启动从传输提供程序到 MAPI 后台处理程序的入站邮件传输。  <br/> |
|[OpenStatusEntry](ixplogon-openstatusentry.md) <br/> |打开传输提供程序的 status 对象。  <br/> |
|[ValidateState](ixplogon-validatestate.md) <br/> |检查传输提供程序的外部状态。  <br/> |
|[FlushQueues](ixplogon-flushqueues.md) <br/> |请求传输提供程序立即传递所有挂起的入站或出站邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

