---
title: IMAPITableUnadvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.Unadvise
api_type:
- COM
ms.assetid: 19f0dad9-9704-4bbe-a689-9531e7198351
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7de4d3c58d5eeefcf9a82235333da5db4703bc8d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592974"
---
# <a name="imapitableunadvise"></a>IMAPITable::Unadvise

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
取消发送通知之前设置与对[IMAPITable::Advise](imapitable-advise.md)方法的调用。 
  
```cpp
HRESULT Unadvise(
ULONG_PTR ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]通过调用[IMAPITable::Advise](imapitable-advise.md)返回注册连接数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功。
    
## <a name="remarks"></a>注解

使用**IMAPITable::Unadvise**方法释放中**IMAPITable::Advise**，从而取消通知注册到以前的呼叫在_lpAdviseSink_参数中传递 advise 接收器对象的指针。 作为放弃 advise 接收器对象的指针的一部分，调用对象的**IUnknown::Release**方法。 通常，调用**Release** **Unadvise**呼叫期间，但另一个线程如果正在为通知接收器，调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法**释放**调用推迟到**OnNotify**方法返回。 
  
通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 有关表通知的特定信息，请参阅[有关表通知](about-table-notifications.md)。 有关使用**IMAPISupport**方法以支持通知的信息，请参阅[支持的事件通知](supporting-event-notification.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |CContentsTableListCtrl::NotificationOff  <br/> |MFCMAPI 使用**IMAPITable::Unadvise**方法取消表的通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPITable::Advise](imapitable-advise.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

