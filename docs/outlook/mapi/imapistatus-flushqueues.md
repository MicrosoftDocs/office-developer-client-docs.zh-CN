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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5f8396ca84192e485d33fb5a96f641361b717584
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432602"
---
# <a name="imapistatusflushqueues"></a>IMAPIStatus::FlushQueues

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
强制立即上载或下载所有等待发送或接收的邮件。 传输提供程序实现的 MAPI 后台处理程序状态对象和 status 对象支持此方法。
  
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
  
> 实时条目标识符中由_lpTargetTransport_参数指向的字节数。 仅在对 MAPI 后台处理程序的状态对象的调用上设置_cbTargetTransport_参数。 对于传输提供程序的调用, _cbTargetTransport_参数设置为0。 
    
 _lpTargetTransport_
  
> 实时指向传输提供程序的条目标识符的指针, 该传输提供程序将刷新其邮件队列。 仅在对 MAPI 后台处理程序的状态对象的调用上设置_lpTargetTransport_参数。 对于传输提供程序的调用, _lpTargetTransport_参数设置为 NULL。 
    
 _ulFlags_
  
> 实时控制刷新操作的标志的位掩码。 可以设置以下标志:
    
FLUSH_ASYNC_OK 
  
> 刷新操作可以异步发生。 此标志仅适用于 MAPI 后台处理程序的状态对象。 
    
FLUSH_DOWNLOAD 
  
> 应刷新传入邮件队列。
    
FLUSH_FORCE 
  
> 应执行刷新操作, 而不考虑性能降低的可能性。 在目标为异步传输提供程序时, 必须设置此标志。
    
FLUSH_NO_UI 
  
> status 对象不应显示进度指示器。
    
FLUSH_UPLOAD 
  
> 应刷新传出邮件队列。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 刷新操作成功。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作;应允许完成此操作, 否则应将其停止, 然后才能启动此操作。
    
MAPI_E_NO_SUPPORT 
  
> status 对象不支持此操作, 正如 status 对象的**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中缺少 STATUS_FLUSH_QUEUES 标志所指示的那样。
    
## <a name="remarks"></a>说明

**IMAPIStatus:: FlushQueues**方法请求 MAPI 后台处理程序或传输提供程序立即发送传出队列中的所有邮件或接收传入队列中的所有邮件。 **FlushQueues**仅由 MAPI 后台处理程序状态对象和传输提供程序提供的 status 对象实现。 
  
应为异步请求返回 MAPI_E_BUSY, 以便客户端可以继续工作。 
  
默认情况下, **FlushQueues**是同步操作;在刷新完成之前, 控件不会返回到调用方。 只有 MAPI 后台处理程序执行的刷新操作才可以是异步操作。客户端通过设置 FLUSH_ASYNC_OK 标志来请求此行为。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

远程传输提供程序的**FlushQueues**实现在登录对象的状态行中的**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中设置 bits, 以控制队列的刷新方式。 如果远程查看器通过 FLUSH_UPLOAD 标志, 则**FlushQueues**方法应设置 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位。 如果远程查看器通过 FLUSH_DOWNLOAD 标志, 则**FlushQueues**方法应设置 STATUS_OUTBOUND_ENABLED 和 STATUS_OUTBOUND_ACTIVE 位。 **FlushQueues**应返回 S_OK。 然后, MAPI 后台处理程序将启动相应的操作来上载和下载邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

对 MAPI 后台处理程序状态对象的调用是一种将所有邮件传输到相应的传输提供程序或从相应的传输提供程序传输的指令。 当您调用单个传输提供程序的状态对象时, 只有该提供程序的消息会受到影响。
  
## <a name="see-also"></a>另请参阅



[PidTagResourceMethods 规范属性](pidtagresourcemethods-canonical-property.md)
  
[PidTagStatusCode 规范属性](pidtagstatuscode-canonical-property.md)
  
[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)

