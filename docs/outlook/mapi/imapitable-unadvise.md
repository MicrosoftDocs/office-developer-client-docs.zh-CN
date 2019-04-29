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
ms.openlocfilehash: da11f15dfe9d269b79f465f01f713de401584962
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430229"
---
# <a name="imapitableunadvise"></a>IMAPITable::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消之前为对[IMAPITable:: Advise](imapitable-advise.md)方法的调用而设置的通知发送。 
  
```cpp
HRESULT Unadvise(
ULONG_PTR ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> 实时对[IMAPITable:: Advise](imapitable-advise.md)的调用返回的注册连接数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功。
    
## <a name="remarks"></a>说明

使用**imapitable:: Unadvise**方法释放指向在上一次调用**IMAPITable:: advise**的_lpAdviseSink_参数中传递的通知接收器对象的指针, 从而取消通知注册。 在舍弃指向通知接收器对象的指针的过程中, 将调用对象的**IUnknown:: Release**方法。 通常, **release**在**Unadvise**调用期间调用, 但如果另一个线程正在调用通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 则**释放**调用将延迟到**OnNotify**方法返回。 
  
有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 有关表通知的具体信息, 请参阅[关于表通知](about-table-notifications.md)。 有关使用**IMAPISupport**方法支持通知的信息, 请参阅[支持事件通知](supporting-event-notification.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> |CContentsTableListCtrl:: NotificationOff  <br/> |MFCMAPI 使用**IMAPITable:: Unadvise**方法取消对表的通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPITable::Advise](imapitable-advise.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

