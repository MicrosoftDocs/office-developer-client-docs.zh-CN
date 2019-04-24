---
title: IMAPISessionAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.Advise
api_type:
- COM
ms.assetid: a6a6b6b1-31e2-4899-a5fe-74d5d1c2ccfc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d5d87d7be9cb3524445107e975a298d4afd5bf98
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338617"
---
# <a name="imapisessionadvise"></a>IMAPISession::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册以接收影响会话的指定事件的通知。
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向通讯簿或邮件存储对象的条目标识符的指针, 该标识符应生成哪些通知, 或者为 NULL, 这表示客户端正在注册以接收有关仅影响会话的事件的通知。 
    
 _ulEventMask_
  
> 实时指示客户端所关注的通知事件类型的值掩码, 应包括在注册中。 如果_lpEntryID_为 NULL, 则 MAPI 会自动为仅影响会话的关键错误事件注册客户端。 当_lpEntryID_指向条目标识符时, 以下值对_ulEventMask_参数有效: 
    
fnevCriticalError 
  
> 注册有关严重错误 (如内存不足) 的通知。
    
fnevExtended 
  
> 注册有关特定通讯簿或邮件存储提供程序的特定事件的通知, 以及关于会话关闭的通知。
    
fnevNewMail 
  
> 注册有关新邮件到达的通知。 
    
fnevObjectCreated 
  
> 注册有关创建新对象的通知。
    
fnevObjectCopied
  
> 注册有关要复制的对象的通知。
    
fnevObjectDeleted
  
> 注册有关要删除的对象的通知。
    
fnevObjectModified
  
> 注册有关要修改的对象的通知。
    
fnevObjectMoved
  
> 注册有关要移动的对象的通知。
    
fnevSearchComplete
  
> 注册有关搜索操作完成的通知。
    
 _lpAdviseSink_
  
> 实时指向接收后续通知的通知接收器对象的指针。 此通知接收器对象必须已分配。
    
 _lpulConnection_
  
> 排除一个指向非零数字的指针, 该数字表示呼叫者的通知接收器对象和会话之间的连接。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注册成功。
    
MAPI_E_INVALID_ENTRYID 
  
> _lpEntryID_指向的条目标识符不代表有效的条目标识符。 
    
MAPI_E_NO_SUPPORT 
  
> 负责_lpEntryID_指向的条目标识符的服务提供程序不支持在_ulEventMask_参数中指定的事件类型或不支持通知。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 配置文件中的任何服务提供程序都不能处理_lpEntryID_指向的条目标识符。 
    
## <a name="remarks"></a>注解

**IMAPISession:: Advise**方法在呼叫者的通知接收器对象、会话和服务提供商 (可选) 之间建立连接。 当在_ulEventMask_参数中指定的一个或多个事件发生于_lpEntryID_指向的对象时, 此连接用于将通知发送到通知接收器。 当_lpEntryID_为 NULL 时, 目标对象为会话, 并且仅发送严重错误和扩展事件的通知。 
  
当_lpEntryID_指向有效的条目标识符时, MAPI 会调用属于负责服务提供商的 logon 对象的**Advise**方法。 例如, 如果_lpEntryID_指向通讯组列表的条目标识符, 则 MAPI 会调用相应的通讯簿提供程序的[IABLogon:: Advise](iablogon-advise.md)方法。 
  
若要发送通知, 服务提供商或 MAPI 将调用已注册的通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。 **OnNotify**的参数之一是通知结构, 它包含描述特定事件的信息。
  
## <a name="notes-to-callers"></a>给调用方的说明

在支持多个执行线程的系统上, 也可以随时在任何线程上对**OnNotify**进行调用。 如果您需要确保仅在特定的线程上的特定时间发生通知, 请调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数来生成您传递给**advise**方法的建议接收器对象。 
  
若要确定客户端注销的时间, 请通过调用_lpEntryID_设置为 NULL 并将_cbEntryID_设置为0的**建议**, 在服务提供程序中注册通知。 当注销发生时, 您将收到 fnevExtended 通知。 
  
在已成功调用**建议**之后且[IMAPISession:: Unadvise](imapisession-unadvise.md)已被调用以取消注册之前, 请释放您的建议接收器对象, 除非您有特定的长期用途。 
  
有关通知过程的概述, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
有关处理通知的详细信息, 请参阅[处理通知](handling-notifications.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|BaseDialog  <br/> |CBaseDialog:: OnNotificationsOn  <br/> |MFCMAPI 使用**IMAPISession:: Advise**方法为会话注册通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IABLogon::Advise](iablogon-advise.md)
  
[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISession::Unadvise](imapisession-unadvise.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 中的事件通知](event-notification-in-mapi.md)

