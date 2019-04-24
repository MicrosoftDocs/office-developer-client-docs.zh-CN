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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2ed8bace97dee3842243ed835769e80e8aaf6b03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329482"
---
# <a name="imapiformadvise"></a>IMAPIForm::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册表单查看器, 以获取有关影响表单的事件的通知。
  
```cpp
HRESULT Advise(
  LPMAPIVIEWADVISESINK pAdvise,
  ULONG FAR * pulConnection
);
```

## <a name="parameters"></a>参数

 _pAdvise_
  
> 实时指向用于接收后续通知的视图建议接收器对象的指针。 
    
 _pulConnection_
  
> 排除指向表示成功的通知注册的非零值的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注册成功。
    
E_OUTOFMEMORY 
  
> 由于内存不足, 注册未成功。
    
## <a name="remarks"></a>注解

表单查看者调用表单的**IMAPIForm:: Advise**方法, 以便在表单发生更改时注册通知。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

保留在_pAdvise_参数中传递的视图建议接收器指针的副本, 以便在事件发生时可以使用该副本调用相应的[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md)方法。 调用 view advise sink [IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)方法以保留指针, 直到通知注册被取消。 将_pulConnection_参数的内容设置为非零数字。 
  
许多窗体都实现帮助程序对象来处理注册和随后发生的事件通知。 
  
有关常规通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
有关通知和窗体的详细信息, 请参阅[发送和接收表单通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIForm::Unadvise](imapiform-unadvise.md)
  
[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MAPI 中的事件通知](event-notification-in-mapi.md)
  
[发送和接收表单通知](sending-and-receiving-form-notifications.md)

