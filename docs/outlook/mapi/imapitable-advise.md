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
ms.openlocfilehash: 781146193748cdd9408a3320e90a73a070ced2af
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775704"
---
# <a name="imapitableadvise"></a>IMAPITable::Advise

  
  
**适用于**： Outlook 
  
注册接收通知的影响表指定事件的 advise 接收器对象。
  
```cpp
HRESULT Advise(
ULONG ulEventMask,
LPMAPIADVISESINK lpAdviseSink,
ULONG_PTR FAR * lpulConnection
);
```

## <a name="parameters"></a>参数

 _ulEventMask_
  
> [in]指示将生成通知的事件类型的值。 下面的值是有效的：
    
 `fnevTableModified`
  
 _lpAdviseSink_
  
> [in]指向 advise 接收器对象接收随后进行通知的指针。 此 advise 接收器对象必须已分配。
    
 _lpulConnection_
  
> [输出]为非零值，该值代表成功通知注册的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功完成通知注册。
    
MAPI_E_NO_SUPPORT 
  
> 表实现不支持为其行和列的更改，或不支持通知。
    
## <a name="remarks"></a>说明

使用**IMAPITable::Advise**方法注册的提供程序通知回调中实现一个 table 对象。 当对 table 对象发生了更改时，提供程序将检查以了解哪些事件掩码位_ulEventMask_参数中的设置，因此发生更改的类型。 如果位设置，然后提供程序调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法所指示的报告，事件将_lpAdviseSink_参数 advise 接收器对象。 数据传递给**OnNotify**例程通知结构中介绍的事件。 
  
更改该对象，该调用期间或任何以下时，可能会发生**OnNotify**调用。 支持多个线程的执行系统，在调用**OnNotify**可以发生任何线程上。 若要打开到一个处理更安全的时机在可能发生的**OnNotify**调用一种方法，为提供程序应使用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数。 
  
若要提供通知，提供程序实施**Advise**需要保留一份指针到_lpAdviseSink_告知接收器对象;为此，请调用通知接收器来维护其对象的指针，直到[IMAPITable::Unadvise](imapitable-unadvise.md)方法的调用被取消通知注册的**IUnknown::AddRef**方法。 **Advise**实现应分配的通知注册的连接数并返回_lpulConnection_参数中之前调用此连接号码**AddRef** 。 服务提供商可以释放 advise 接收器对象之前取消注册，但他们必须释放直到连接数 * * Unadvise * * 已被调用。 
  
调用**Advise**已成功完成之后，并在 * * Unadvise * * 已调用，客户端必须先为准备 advise 接收器对象，必须释放。 **Advise**返回，除非它为其具有特定的长期使用后，客户端应因此释放其 advise 接收器对象。 
  
通知的异步行为，由于更改表列设置的实现可以接收通知与上一列顺序组织的信息。 例如，可能只需已从容器中删除一条消息的返回表格行。 此类将通知发送时所做更改列设置和发送有关该产品的信息但尚未该信息尚未更新通知表视图。
  
通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 有关表通知的特定信息，请参阅[有关表通知](about-table-notifications.md)。 有关使用**IMAPISupport**方法以支持通知的信息，请参阅[支持的事件通知](supporting-event-notification.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContestTableListCtrl::NotificationOn  <br/> |MFCMAPI 使用**IMAPITable::Advise**方法注册通知，以允许保持当前表视图。  <br/> |
   
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPITable::Unadvise](imapitable-unadvise.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

