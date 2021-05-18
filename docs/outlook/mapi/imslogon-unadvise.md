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
  
通过调用 [IMSLogon：：Advise](imslogon-advise.md) 方法，删除对象对之前建立的邮件存储更改通知的注册。 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]通过调用 **IMSLogon：：Advise** 返回的注册连接数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

消息存储提供程序实现 **IMSLogon：：Unadvise** 方法，以释放指向在上一次调用 **IMSLogon：：Advise** 时传入 _lpAdviseSink_ 参数中的通知接收对象的指针，从而取消通知注册。 作为放弃指向建议接收对象的指针的一部分，将调用对象的 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) 方法。 通常， **在** 非企业调用 **期间调用** Release。 但是，如果另一个线程正在调用通知接收器对象的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法， **则 Release** 调用将延迟到 **OnNotify** 方法返回。 
  
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMSLogon::Advise](imslogon-advise.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

