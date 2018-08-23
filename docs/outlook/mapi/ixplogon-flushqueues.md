---
title: IXPLogonFlushQueues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.FlushQueues
api_type:
- COM
ms.assetid: c1f630c6-9e95-49c0-9757-4685c98184dc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 961ac2d26cd58e625c35d00bd1216cdee2ce57a0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584728"
---
# <a name="ixplogonflushqueues"></a>IXPLogon::FlushQueues

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
传输提供程序立即提供所有挂起的入站或出站消息的请求。
  
```cpp
HRESULT FlushQueues(
  ULONG_PTR ulUIParam,
  ULONG cbTargetTransport,
  LPENTRYID lpTargetTransport,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]任何对话框的父窗口或该方法显示的窗口句柄。
    
 _cbTargetTransport_
  
> [in]保留;必须为零。
    
 _lpTargetTransport_
  
> [in]保留;必须为 NULL。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何完成消息队列刷新。 可以设置以下标志：
    
FLUSH_DOWNLOAD 
  
> 应刷新的入站的消息队列。
    
FLUSH_FORCE 
  
> 传输提供程序应处理此请求中，如果可能，即使这样做，以便为较长时间。 
    
FLUSH_NO_UI 
  
> 传输提供程序不应显示的用户界面。
    
FLUSH_UPLOAD 
  
> 应刷新的出站消息队列。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IXPLogon::FlushQueues**方法以指出 MAPI 后台处理程序即将开始处理邮件的传输提供程序。 传输提供程序应调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法，以便其状态的行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中设置其状态的适当的位。 更新其状态的行之后, 传输提供程序应**FlushQueues**呼叫返回 S_OK。 MAPI 后台处理程序然后启动发送消息，与正在同步到 MAPI 后台处理程序的操作。 
  
若要支持其[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法的实现，MAPI 后台处理程序调用**IXPLogon::FlushQueues**所有登录对象的为配置文件会话中运行的活动传输提供程序。 由于客户端应用程序调用**IMAPIStatus::FlushQueues**调用传输提供程序的**FlushQueues**方法时，消息处理发生异步到客户端。
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

