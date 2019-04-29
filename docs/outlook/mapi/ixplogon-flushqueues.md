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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fb26c7f366ce6a262362001773e825c60d0e4ec3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421968"
---
# <a name="ixplogonflushqueues"></a>IXPLogon::FlushQueues

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
请求传输提供程序立即传递所有挂起的入站或出站邮件。
  
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
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。
    
 _cbTargetTransport_
  
> 实时保留必须为零。
    
 _lpTargetTransport_
  
> 实时保留必须为 NULL。
    
 _ulFlags_
  
> 实时用于控制如何完成邮件队列刷新的标志的位掩码。 可以设置以下标志:
    
FLUSH_DOWNLOAD 
  
> 应刷新入站邮件队列或队列。
    
FLUSH_FORCE 
  
> 如果可能, 传输提供程序应处理此请求 (如果可能), 即使这样做很耗时。 
    
FLUSH_NO_UI 
  
> 传输提供程序不应显示用户界面。
    
FLUSH_UPLOAD 
  
> 应刷新出站邮件队列或队列。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>说明

mapi 后台处理程序调用**IXPLogon:: FlushQueues**方法, 以告知 MAPI 后台处理程序即将开始处理邮件的传输提供程序。 传输提供程序应调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法, 以在其状态行的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中为其状态设置一个适当的位。 更新其状态行后, 传输提供程序应返回**FlushQueues**调用的 S_OK。 mapi 后台处理程序随后开始发送邮件, 并将操作同步到 MAPI 后台处理程序。 
  
若要支持其[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)方法的实现, MAPI 后台处理程序会调用在配置文件会话中运行的活动传输提供程序的所有登录对象的**IXPLogon:: FlushQueues** 。 当传输提供程序的**FlushQueues**方法作为客户端应用程序调用**IMAPIStatus:: FlushQueues**时调用时, 邮件处理将异步发生到客户端。
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

