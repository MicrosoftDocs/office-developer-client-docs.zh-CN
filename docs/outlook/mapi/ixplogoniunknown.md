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
ms.openlocfilehash: ecfbf33641c86d4f162c521466ca2bf0b79a61d5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581403"
---
# <a name="ixplogon--iunknown"></a>IXPLogon : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 后台处理程序访问提供传输提供程序。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|由公开：  <br/> |传输登录对象  <br/> |
|通过实现：  <br/> |传输提供程序  <br/> |
|调用：  <br/> |MAPI 后台处理程序  <br/> |
|接口标识符：  <br/> |IID_IXPLogon  <br/> |
|指针类型：  <br/> |LXPLOGON  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[AddressTypes](ixplogon-addresstypes.md) <br/> |返回的收件人的传输提供程序处理的类型。  <br/> |
|**RegisterOptions** <br/> | *不受支持或记录。*  <br/> |
|[TransportNotify](ixplogon-transportnotify.md) <br/> |信号传输提供程序有关哪些请求发送通知的事件的匹配项。  <br/> |
|[空闲时间](ixplogon-idle.md) <br/> |指示系统空闲，启用传输提供程序执行低优先级操作。  <br/> |
|[TransportLogoff](ixplogon-transportlogoff.md) <br/> |启动注销过程。  <br/> |
|[SubmitMessage](ixplogon-submitmessage.md) <br/> |指示 MAPI 后台处理程序都有要提供的传输提供程序的消息。  <br/> |
|[EndMessage](ixplogon-endmessage.md) <br/> |通知传输提供程序 MAPI 后台处理程序完成对出站邮件及其处理。  <br/> |
|[投票](ixplogon-poll.md) <br/> |指示的传输提供程序是否已接收到一个或多个入站的邮件。  <br/> |
|[StartMessage](ixplogon-startmessage.md) <br/> |启动入站邮件传输提供程序传输到 MAPI 后台处理程序。  <br/> |
|[OpenStatusEntry](ixplogon-openstatusentry.md) <br/> |打开传输提供程序的状态对象。  <br/> |
|[ValidateState](ixplogon-validatestate.md) <br/> |检查传输提供程序的外部状态。  <br/> |
|[FlushQueues](ixplogon-flushqueues.md) <br/> |传输提供程序立即提供所有挂起的入站或出站消息的请求。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

