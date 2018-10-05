---
title: IMAPIFormUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.Unadvise
api_type:
- COM
ms.assetid: fdda45e2-631d-404c-8af4-bce68df0968b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 770ceb7af98f5271baad65043e013feb353d231a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390469"
---
# <a name="imapiformunadvise"></a>IMAPIForm::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用窗体查看器通过调用[IMAPIForm::Advise](imapiform-advise.md)以前建立取消通知注册。
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]标识要取消此事件的通知注册连接数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 取消注册。
    
E_INVALIDARG 
  
> _UlConnection_参数中传递的连接数不代表有效的注册。 
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIForm::Unadvise**方法取消其第一次调用**IMAPIForm::Advise**方法来建立的通知的注册。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

放弃指针是保存到表单查看器的视图通过调用其[IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法通知接收器。 通常，调用**Release** **Unadvise**呼叫过程中。 但是，如果正在调用[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md)方法之一，另一个线程视图告知接收器，直至**IMAPIViewAdviseSink**方法返回延迟**释放**调用。 
  
## <a name="see-also"></a>另请参阅



[IMAPIForm::Advise](imapiform-advise.md)
  
[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)

