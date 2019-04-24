---
title: IMSLogonLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.Logoff
api_type:
- COM
ms.assetid: 1b0d1b52-6651-4de3-9381-86772d9d52a1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 66ba27d1d333be3217f2a22ca5d53449372c1f31
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348872"
---
# <a name="imslogonlogoff"></a>IMSLogon::Logoff

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注销邮件存储提供程序。 
  
```cpp
HRESULT Logoff(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> 实时保留必须是指向零的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>注解

邮件存储提供程序实现**IMSLogon:: 注销**方法以强制关闭邮件存储提供程序。 **IMSLogon::** 在以下情况下会调用注销: 
  
- 尽管 MAPI 在调用[IMAPISession:: 注销](imapisession-logoff.md)方法后注销客户端。 
    
- MAPI 注销邮件存储提供程序时。 在这种情况下, **IMSLogon:: 注销**在处理[IMsgStore:: StoreLogoff](imsgstore-storelogoff.md)或 IUnknown 时创建的支持对象的[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法是邮件存储提供程序在处理:: 或 IUnknown 过程中创建的支持对象的 Release 方法: **** 对邮件存储对象的 Release 方法调用。 
    
## <a name="see-also"></a>另请参阅



[IMAPISession::Logoff](imapisession-logoff.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)
  
[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)
  
[IMSProvider::Logon](imsprovider-logon.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

