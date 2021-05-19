---
title: IMAPITableAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.Advise
api_type:
- COM
ms.assetid: e8b5d21e-dc14-4b61-96b3-a51bcfa0d232
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c9401c163c74ab303ec39c147e0432d1979426b8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418811"
---
# <a name="imapitableadvise"></a>IMAPITable::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册通知接收对象以接收影响表的指定事件的通知。
  
```cpp
HRESULT Advise(
ULONG ulEventMask,
LPMAPIADVISESINK lpAdviseSink,
ULONG_PTR FAR * lpulConnection
);
```

## <a name="parameters"></a>参数

 _ulEventMask_
  
> [in]指示将生成通知的事件类型的值。 只有以下值有效：
    
 `fnevTableModified`
  
 _lpAdviseSink_
  
> [in]指向接收后续通知的建议接收对象的指针。 此通知接收器对象必须已分配。
    
 _lpulConnection_
  
> [out]指向表示成功通知注册的非零值的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册成功完成。
    
MAPI_E_NO_SUPPORT 
  
> 表实现要么不支持更改其行和列，要么不支持通知。
    
## <a name="remarks"></a>备注

使用 **IMAPITable：：Advise** 方法注册在提供程序中实现的表对象，以用于通知回调。 每当表对象发生变化时，提供程序都会检查在  _ulEventMask_ 参数中设置了哪些事件掩码位，从而查看发生了哪种类型的更改。 如果设置了位，则提供程序将调用 _由 lpAdviseSink_ 参数指示的建议接收器对象的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法以报告事件。 在通知结构中传递给 **OnNotify** 例程的数据描述事件。 
  
调用 **OnNotify** 可以在更改对象的调用期间或以下任何时间发生。 在支持多个执行线程的系统上，对 **OnNotify** 的调用可以在任何线程上发生。 为了能够将可能在不及时发生的 **OnNotify** 调用转换为更安全地处理调用，提供程序应该使用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数。 
  
若要提供通知，实现 **Advise** 的提供程序需要保留指向  _lpAdviseSink_ advise 接收器对象的指针的副本;为此，它会调用通知接收器的 **IUnknown：：AddRef** 方法，以维护其对象指针，直到通过调用 [IMAPITable：：Unadvise](imapitable-unadvise.md) 方法取消通知注册。 Advise 实现应为通知注册分配一个连接号码，并在此连接号码上调用 **AddRef，** 然后再在 _lpulConnection_ 参数中返回它。 服务提供商可以在取消注册之前释放通知接收器对象，但在调用 ** Unadvise ** 之前，它们不得释放连接号。 
  
在成功调用 **Advise** 之后，在调用 ** Unadvise ** 之前，必须准备客户端以释放通知接收器对象。 因此，客户端应在 Advise 返回后释放其 **advise** 接收器对象，除非它具有特定的长期用途。 
  
由于通知的异步行为，更改表列设置的实现可以接收具有按上一列顺序组织的信息的通知。 例如，对于刚刚从容器中删除的邮件，可能会返回一个表行。 当列设置更改和有关它的信息已发送，但尚未使用该信息更新通知表视图时，将发送此类通知。
  
有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。 有关表通知的特定信息，请参阅关于 [表通知](about-table-notifications.md)。 有关使用 **IMAPISupport** 方法支持通知的信息，请参阅 [Supporting Event Notification。](supporting-event-notification.md)
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContestTableListCtrl：：NotificationOn  <br/> |MFCMAPI 使用 **IMAPITable：：Advise** 方法注册通知，以允许表视图保持最新。  <br/> |
   
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPITable::Unadvise](imapitable-unadvise.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

