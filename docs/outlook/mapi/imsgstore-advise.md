---
title: IMsgStoreAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.Advise
api_type:
- COM
ms.assetid: 8c57e743-a798-4e39-a61a-46dff8b1ac7c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b4abef731541e308b2c2ebc6f4aaddf4458e257
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317323"
---
# <a name="imsgstoreadvise"></a>IMsgStore::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册以接收对邮件存储区产生影响的指定事件的通知。
  
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
  
> 实时一个指针, 指向有关应生成其通知的文件夹或消息的条目标识符, 或**为 null**。 如果将_lpEntryID_设置为 NULL,**建议**在整个邮件存储区上注册通知。 
    
 _ulEventMask_
  
> 实时指示呼叫者感兴趣且应包含在注册中的通知事件类型的值掩码。 有与每种类型的事件相关联的相应[通知](notification.md)结构, 其中包含有关该事件的信息。 以下是_ulEventMask_参数的有效值: 
    
 _fnevCriticalError_
  
> 注册有关严重错误 (如内存不足) 的通知。
    
 _fnevExtended_
  
> 注册有关特定邮件存储提供程序特定的事件的通知。
    
 _fnevNewMail_
  
> 注册有关新邮件到达的通知。 
    
 _fnevObjectCreated_
  
> 注册有关创建新文件夹或邮件的通知。
    
 _fnevObjectCopied_
  
> 注册有关要复制的文件夹或邮件的通知。
    
 _fnevObjectDeleted_
  
> 注册有关要删除的文件夹或邮件的通知。
    
 _fnevObjectModified_
  
> 注册有关要修改的文件夹或邮件的通知。
    
 _fnevObjectMoved_
  
> 注册有关要移动的文件夹或邮件的通知。
    
 _fnevSearchComplete_
  
> 注册有关搜索操作完成的通知。
    
 _lpAdviseSink_
  
> 实时指向接收后续通知的通知接收器对象的指针。 此通知接收器对象必须已分配。
    
 _lpulConnection_
  
> 排除一个指向非零数字的指针, 该数字表示呼叫者的通知接收器对象和会话之间的连接。 
    
 _lpAdviseSink_
  
> 实时指向接收后续通知的通知接收器对象的指针。 此通知接收器对象必须已分配。 
    
 _lpulConnection_
  
> 排除一个指针, 指向表示呼叫者的通知接收器对象和邮件存储区之间的连接的非零连接号码。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注册成功。
    
MAPI_E_NO_SUPPORT 
  
> 邮件存储提供程序不支持通过邮件存储区注册通知。
    
## <a name="remarks"></a>注解

**IMsgStore:: Advise**方法在调用方的通知接收器对象与邮件存储区或邮件存储区中的对象之间建立连接。 此连接用于在通知源对象发生一个或多个事件 (如_ulEventMask_参数中指定) 时, 将通知发送到通知接收器。 当_lpEntryID_参数指向有效的条目标识符时, 建议源为此条目标识符标识的对象。 当_lpEntryID_为 NULL 时, 建议源为邮件存储区。 
  
若要发送通知, 邮件存储提供程序或 MAPI 将调用已注册的通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。 **OnNotify**的参数之一是通知结构, 它包含描述特定事件的信息。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

你可以在 MAPI 中支持带有或没有帮助的通知。 MAPI 具有三个用于帮助服务提供程序实现通知的支持对象方法: [IMAPISupport:: 订阅](imapisupport-subscribe.md)、 [IMAPISupport:: 退订](imapisupport-unsubscribe.md)和[IMAPISupport:: Notify](imapisupport-notify.md)。 如果选择使用 MAPI 支持方法, 请在调用**Advise**方法时呼叫**订阅**, 并释放_lpAdviseSink_指针。 
  
如果选择支持自己的通知, 请调用_lpAdviseSink_参数所代表的 "通知接收器" 的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法, 以保留此指针的副本。 维护此副本, 直到调用[IMsgStore:: Unadvise](imsgstore-unadvise.md)方法以取消注册。 
  
无论您如何支持通知, 请为通知注册分配非零连接号码, 并将其返回到_lpulConnection_参数中。 在**Unadvise**已被调用并完成之前, 请勿释放此连接号码。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在支持多个执行线程的系统上, 也可以随时在任何线程上对**OnNotify**进行调用。 如果您必须确保仅在特定的线程上的特定时间发生通知, 请调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数来生成您传递给**建议**的建议接收器对象。 
  
在对**建议**的调用成功且已调用**Unadvise**以取消注册之前, 请准备好要释放的通知接收器对象。 除非您有特定的长期用途, 否则应在**建议**返回后释放建议的接收器对象。 
  
有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
有关处理通知的详细信息, 请参阅[处理通知](handling-notifications.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|BaseDialog  <br/> |CBaseDialog:: OnNotificationsOn  <br/> |MFCMAPI 使用**IMsgStore:: Advise**方法为整个邮件存储区注册通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMsgStore::Unadvise](imsgstore-unadvise.md)
  
[NOTIFICATION](notification.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

