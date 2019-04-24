---
title: IMSLogonUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.Unadvise
api_type:
- COM
ms.assetid: 440d61c4-b69a-4010-a22b-0c9c5c376fbc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9172d4956e78ac31cd15d69e70d05c127a474ca5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317274"
---
# <a name="imslogonunadvise"></a>IMSLogon::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用对[IMSLogon:: Advise](imslogon-advise.md)方法的调用, 删除以前建立的邮件存储区更改通知的对象注册。 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> 实时通过调用**IMSLogon:: 建议**返回的注册连接的号码。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

邮件存储提供程序实现**IMSLogon:: Unadvise**方法, 以释放指向在上一次调用**IMSLogon:: 建议**的_lpAdviseSink_参数中传递的通知接收器对象的指针, 从而取消通知注册. 在舍弃指向通知接收器对象的指针的过程中, 将调用对象的[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。 通常情况下, 在**Unadvise**调用过程中调用**Release** 。 但是, 如果另一个线程在调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法的建议接收器对象的过程中, 则**释放**调用将延迟到**OnNotify**方法返回为止。 
  
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMSLogon::Advise](imslogon-advise.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

