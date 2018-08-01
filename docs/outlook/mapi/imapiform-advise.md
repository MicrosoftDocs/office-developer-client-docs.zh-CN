---
title: IMAPIFormAdvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.Advise
api_type:
- COM
ms.assetid: 961318d6-bebe-4f4b-98ff-921cafc68d24
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b5347205e10b44d62a7e11cbe2f4179970f1bd64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775367"
---
# <a name="imapiformadvise"></a>IMAPIForm::Advise

  
  
**适用于**： Outlook 
  
注册的窗体查看有关影响窗体的事件通知。
  
```cpp
HRESULT Advise(
  LPMAPIVIEWADVISESINK pAdvise,
  ULONG FAR * pulConnection
);
```

## <a name="parameters"></a>参数

 _pAdvise_
  
> [in]指向视图的建议接收器对象接收随后进行通知。 
    
 _pulConnection_
  
> [输出]指向为非零值，该值代表成功的通知注册的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注册成功。
    
E_OUTOFMEMORY 
  
> 由于内存不足，注册成功。
    
## <a name="remarks"></a>说明

表单查看器调用窗体**IMAPIForm::Advise**方法来注册到窗体发生更改时通知。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

保留副本的视图的建议，以便您可以使用该事件发生时调用相应的[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md)方法_pAdvise_参数中传递的接收器指针。 呼叫视图建议接收器的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx)方法保留指针，直到通知注册被取消。 设为非零值数_pulConnection_参数的内容。 
  
多个窗体实现帮助程序对象来处理注册和事件的后续的通知。 
  
有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
有关通知和窗体的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIForm::Unadvise](imapiform-unadvise.md)
  
[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MAPI 中的事件通知](event-notification-in-mapi.md)
  
[发送和接收表单通知](sending-and-receiving-form-notifications.md)

