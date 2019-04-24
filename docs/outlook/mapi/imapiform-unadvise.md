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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 770ceb7af98f5271baad65043e013feb353d231a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329468"
---
# <a name="imapiformunadvise"></a>IMAPIForm::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过调用[IMAPIForm:: 建议](imapiform-advise.md)取消对以前建立的表单查看器的通知的注册。
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> 实时标识要取消的通知注册的连接号。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已取消注册。
    
E_INVALIDARG 
  
> 传递给_ulConnection_参数的连接号码不代表有效的注册。 
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIForm:: Unadvise**方法, 以取消注册, 以便通过调用**IMAPIForm:: Advise**方法首先建立的通知。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

通过调用其[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法来放弃您为表单查看器的视图建议接收器所包含的指针。 通常情况下, 在**Unadvise**调用过程中调用**Release** 。 但是, 如果另一个线程正在调用视图建议接收器的[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md)方法之一, 则延迟**释放**调用, 直到**IMAPIViewAdviseSink**方法返回。 
  
## <a name="see-also"></a>另请参阅



[IMAPIForm::Advise](imapiform-advise.md)
  
[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)

