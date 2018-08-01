---
title: IMAPIStatusFlushQueues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus.FlushQueues
api_type:
- COM
ms.assetid: d6b01a91-b452-4b2c-9802-698e7b0f4169
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d6c221ae307edb9d84cfcc0026660ea4bce7fadd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775582"
---
# <a name="imapistatusflushqueues"></a>IMAPIStatus::FlushQueues

  
  
**适用于**： Outlook 
  
强制等待发送或接收立即上载或下载的所有邮件。 MAPI 后台处理程序状态对象和传输提供程序实现的状态对象支持此方法。
  
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
  
> [in]在_lpTargetTransport_参数指向的项标识符的字节数。 _CbTargetTransport_参数仅在调用 MAPI 后台处理程序的状态对象上设置。 对于到传输提供程序的调用， _cbTargetTransport_参数设置为 0。 
    
 _lpTargetTransport_
  
> [in]指向的传输提供程序刷新其消息队列的项标识符的指针。 _LpTargetTransport_参数仅在调用 MAPI 后台处理程序的状态对象上设置。 对于到传输提供程序的调用， _lpTargetTransport_参数设置为 NULL。 
    
 _ulFlags_
  
> [in]位掩码的标志的控件的刷新操作。 可以设置以下标志：
    
FLUSH_ASYNC_OK 
  
> 异步出现的刷新操作。 此标志仅适用于 MAPI 后台处理程序的状态对象。 
    
FLUSH_DOWNLOAD 
  
> 应刷新传入的消息队列。
    
FLUSH_FORCE 
  
> 刷新操作应无论如何，而不考虑的性能降低进行。 目标异步传输提供程序时，必须设置此标志。
    
FLUSH_NO_UI 
  
> 状态对象不应显示进度指示器。
    
FLUSH_UPLOAD 
  
> 应刷新的传出消息队列。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 刷新操作已成功。
    
MAPI_E_BUSY 
  
> 正在进行; 另一个操作应允许其完成，或者它应停止，可以启动此操作之前。
    
MAPI_E_NO_SUPPORT 
  
> 状态对象不支持此操作，如缺少 STATUS_FLUSH_QUEUES 标志状态对象的**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中所示。
    
## <a name="remarks"></a>说明

**IMAPIStatus::FlushQueues**方法请求的 MAPI 后台处理程序传输提供程序立即发送传出队列中的所有邮件或从传入的队列接收所有的消息。 **FlushQueues**是只能通过 MAPI 后台处理程序状态对象和由传输提供程序提供的状态对象实现的。 
  
应异步请求返回 MAPI_E_BUSY，以便客户端可以继续工作。 
  
默认情况下**FlushQueues**是同步操作;刷新已完成，直到控件不返回到呼叫者。 仅由 MAPI 后台处理程序执行的刷新操作可以是异步的;客户端通过设置 FLUSH_ASYNC_OK 标志请求此行为。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

远程传输提供程序的实现**FlushQueues**登录对象的状态行来控制如何刷新队列中的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中设置了位。 如果远程查看器传入 FLUSH_UPLOAD 标志， **FlushQueues**方法应设置 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位。 如果远程查看器传入 FLUSH_DOWNLOAD 标志， **FlushQueues**方法应设置 STATUS_OUTBOUND_ENABLED 和 STATUS_OUTBOUND_ACTIVE 位。 **FlushQueues**然后应返回 S_OK。 然后，MAPI 后台处理程序将启动上载和下载邮件的相应操作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

MAPI 后台处理程序状态对象调用是指令传输到或从适当的传输提供程序的所有邮件。 在调用的单个传输提供程序的状态对象时，会影响只有该提供程序的邮件。
  
## <a name="see-also"></a>另请参阅



[PidTagResourceMethods 规范属性](pidtagresourcemethods-canonical-property.md)
  
[PidTagStatusCode 规范属性](pidtagstatuscode-canonical-property.md)
  
[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)

