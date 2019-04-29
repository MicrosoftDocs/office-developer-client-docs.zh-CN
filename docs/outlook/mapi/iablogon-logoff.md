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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: af3c1f5135e90274c0251c5a0addf339c14f36c0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416396"
---
# <a name="iablogonlogoff"></a>IABLogon::Logoff

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启动注销过程。
  
```cpp
HRESULT Logoff(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功启动注销过程。
    
## <a name="remarks"></a>说明

注销过程通常在客户端调用[IMAPISession:: 注销](imapisession-logoff.md)方法结束会话时启动。 然后, MAPI 会调用每个通讯簿提供程序的**IABLogon:: 注销**方法, 以启动注销过程。 
  
**IABLogon:: 注销**方法执行以下操作: 
  
- 释放所有打开的对象, 例如任意子对象或 status 对象。
    
- 释放提供程序的支持对象。
    
有关通讯簿提供程序的注销过程的详细信息, 请参阅[关闭服务提供程序](shutting-down-a-service-provider.md)。
  
## <a name="see-also"></a>另请参阅



[IABProvider::Logon](iabprovider-logon.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

