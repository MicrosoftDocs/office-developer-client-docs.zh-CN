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
  
注册一个建议接收器对象, 以接收影响表的指定事件的通知。
  
```cpp
HRESULT Advise(
ULONG ulEventMask,
LPMAPIADVISESINK lpAdviseSink,
ULONG_PTR FAR * lpulConnection
);
```

## <a name="parameters"></a>参数

 _ulEventMask_
  
> 实时值, 该值指示将生成通知的事件的类型。 仅以下值是有效的:
    
 `fnevTableModified`
  
 _lpAdviseSink_
  
> 实时指向要接收后续通知的通知接收器对象的指针。 此通知接收器对象必须已分配。
    
 _lpulConnection_
  
> 排除指向表示成功的通知注册的非零值的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册已成功完成。
    
MAPI_E_NO_SUPPORT 
  
> 表实现不支持对其行和列进行更改, 也不支持通知。
    
## <a name="remarks"></a>说明

使用**IMAPITable:: Advise**方法注册在提供程序中实现的用于通知回调的 table 对象。 每当 table 对象发生更改时, 提供程序都会检查在_ulEventMask_参数中设置的事件掩码位, 从而确定发生的更改类型。 如果设置了一个位, 则提供程序将调用由_lpAdviseSink_参数指示的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 以报告事件。 通知结构中传递给**OnNotify**例程的数据描述了该事件。 
  
调用**OnNotify**可能会在更改对象的调用过程中或在任何时间发生。 在支持多个执行线程的系统上, 对**OnNotify**的调用可以出现在任何线程上。 若要对可能在 inopportune 时发生的**OnNotify**的调用进行更安全地处理的方法, 请参阅[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数。 
  
若要提供通知, 提供程序实现**建议**需要将指针副本保存到_lpAdviseSink_建议接收器对象;为此, 它会调用通知接收器的**IUnknown:: AddRef**方法来维护其对象指针, 直到使用对[IMAPITable:: Unadvise](imapitable-unadvise.md)方法的调用取消通知注册。 **建议**实现应为通知注册分配一个连接号码, 并在此连接号码上调用**AddRef** , 然后再将其返回到_lpulConnection_参数中。 服务提供程序可以在取消注册之前释放通知接收器对象, 但在调用 * * Unadvise * * 之前, 它们不能释放连接号码。 
  
在调用了 "**建议**已成功" 且在 "* * Unadvise * *" 之前调用之后, 客户端必须准备就绪, 才能释放通知接收器对象。 因此, 客户端应在**建议**返回后释放其建议接收器对象, 除非它对其具有特定的长期使用。 
  
由于通知的异步行为, 因此更改表列设置的实现可以接收按上一列顺序组织的信息的通知。 例如, 对于刚刚从容器中删除的邮件, 可能会返回一个表行。 当列设置发生更改时, 将发送此类通知, 并在通知表视图尚未使用该信息更新的情况中对其发送信息。
  
有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 有关表通知的具体信息, 请参阅[关于表通知](about-table-notifications.md)。 有关使用**IMAPISupport**方法支持通知的信息, 请参阅[支持事件通知](supporting-event-notification.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |CContestTableListCtrl:: NotificationOn  <br/> |MFCMAPI 使用**IMAPITable:: Advise**方法注册通知, 以允许表视图保持最新。  <br/> |
   
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPITable::Unadvise](imapitable-unadvise.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

