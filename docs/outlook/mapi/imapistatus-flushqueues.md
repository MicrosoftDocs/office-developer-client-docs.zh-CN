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
  
强制立即上载或下载等待发送或接收的所有邮件。 传输提供程序实现 MAPI 后台处理程序状态对象和状态对象支持此方法。
  
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
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。
    
 _cbTargetTransport_
  
> [in]  _lpTargetTransport_ 参数指向的条目标识符中的字节计数。 _cbTargetTransport_ 参数仅在调用 MAPI 后台处理程序的状态对象时设置。 对于对传输提供程序的调用  _，cbTargetTransport_ 参数设置为 0。 
    
 _lpTargetTransport_
  
> [in]指向要刷新其邮件队列的传输提供程序的条目标识符的指针。 _lpTargetTransport_ 参数仅在调用 MAPI 后台处理程序的状态对象时设置。 对于对传输提供程序的调用  _，lpTargetTransport_ 参数设置为 NULL。 
    
 _ulFlags_
  
> [in]控制刷新操作的标志的位掩码。 可以设置以下标志：
    
FLUSH_ASYNC_OK 
  
> 刷新操作可以异步发生。 此标志仅适用于 MAPI 后台处理程序的状态对象。 
    
FLUSH_DOWNLOAD 
  
> 应刷新传入邮件队列。
    
FLUSH_FORCE 
  
> 无论性能降低的可能性如何，都应执行刷新操作。 当定向异步传输提供程序时，必须设置此标志。
    
FLUSH_NO_UI 
  
> 状态对象不应显示进度指示器。
    
FLUSH_UPLOAD 
  
> 应刷新传出邮件队列。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 刷新操作成功。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作;应允许完成此操作，或者应停止此操作，然后才能启动此操作。
    
MAPI_E_NO_SUPPORT 
  
> status 对象不支持此操作，如状态对象的 PR_RESOURCE_METHODS ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)属性中缺少STATUS_FLUSH_QUEUES 标志) 。
    
## <a name="remarks"></a>备注

**IMAPIStatus：：FlushQueues** 方法请求 MAPI 后台处理程序或传输提供程序立即发送传出队列中的所有邮件或接收传入队列中的所有邮件。 **FlushQueues** 仅由 MAPI 后台处理程序状态对象和传输提供程序提供的状态对象实现。 
  
MAPI_E_BUSY应返回异步请求，以便客户端可以继续工作。 
  
默认情况下 **，FlushQueues** 是同步操作;控件不会返回到调用方，直到刷新完成。 只有 MAPI 后台处理程序执行的刷新操作可以异步执行;客户端通过设置 FLUSH_ASYNC_OK 请求此行为。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

远程传输提供程序的 **FlushQueues** 实现设置登录对象状态行中 **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中的位，以控制队列的刷新方式。 如果远程查看器通过 FLUSH_UPLOAD 标志 **，FlushQueues** 方法应设置 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位。 如果远程查看器通过 FLUSH_DOWNLOAD 标志 **，FlushQueues** 方法应设置 STATUS_OUTBOUND_ENABLED 和 STATUS_OUTBOUND_ACTIVE 位。 **FlushQueues** 随后应返回S_OK。 然后，MAPI 后台处理程序将启动相应的操作来上载和下载邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

对 MAPI 后台处理程序状态对象的调用是一个指令，指示将所有邮件转移到相应的传输提供程序或从相应的传输提供程序传输所有邮件。 当您调用单个传输提供程序的状态对象时，只会影响该提供商的邮件。
  
## <a name="see-also"></a>另请参阅



[PidTagResourceMethods 规范属性](pidtagresourcemethods-canonical-property.md)
  
[PidTagStatusCode 规范属性](pidtagstatuscode-canonical-property.md)
  
[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)

