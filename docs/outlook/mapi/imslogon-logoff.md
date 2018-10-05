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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 66ba27d1d333be3217f2a22ca5d53449372c1f31
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399233"
---
# <a name="imslogonlogoff"></a>IMSLogon::Logoff

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注销一条消息存储提供程序。 
  
```cpp
HRESULT Logoff(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [in]保留;必须为零的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

消息存储提供程序实现**IMSLogon::Logoff**方法以强制关闭消息存储提供程序。 在下列情况下调用**IMSLogon::Logoff** : 
  
- 同时给[IMAPISession::Logoff](imapisession-logoff.md)方法调用后 MAPI 正在注销客户端。 
    
- MAPI 注销消息存储提供程序时。 在这种情况下， **IMSLogon::Logoff**称为 MAPI 处理的消息存储提供程序创建处理[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)或**IUnknown 时支持对象的[IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法的一部分::发行版**消息存储对象上的方法调用。 
    
## <a name="see-also"></a>另请参阅



[IMAPISession::Logoff](imapisession-logoff.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)
  
[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)
  
[IMSProvider::Logon](imsprovider-logon.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

