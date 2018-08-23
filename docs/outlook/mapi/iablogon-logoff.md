---
title: IABLogonLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.Logoff
api_type:
- COM
ms.assetid: a36465e2-7be9-4bd6-8091-685f0a045aa9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a20fdd45c39cc2147f8fdc7b1998ff6d1b0797bb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586205"
---
# <a name="iablogonlogoff"></a>IABLogon::Logoff

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
启动注销过程。
  
```cpp
HRESULT Logoff(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注销过程已成功启动。
    
## <a name="remarks"></a>注解

客户端调用[IMAPISession::Logoff](imapisession-logoff.md)方法来结束会话时，通常被启动注销过程。 MAPI 然后调用每个通讯簿提供程序的**IABLogon::Logoff**方法来启动注销过程。 
  
**IABLogon::Logoff**方法将执行以下操作： 
  
- 释放所有打开的对象，如任何子对象或状态对象。
    
- 释放提供程序的支持对象。
    
通讯簿提供程序的注销过程的详细信息，请参阅[关机的情况下 Service Provider](shutting-down-a-service-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IABProvider::Logon](iabprovider-logon.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

