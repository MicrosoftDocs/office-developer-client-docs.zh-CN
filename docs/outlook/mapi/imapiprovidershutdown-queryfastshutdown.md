---
title: IMAPIProviderShutdownQueryFastShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProviderShutdown.QueryFastShutdown
api_type:
- COM
ms.assetid: 12069912-4b87-4945-9123-51106e0d2d54
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 50b49761cf5923b11a450cbce7b7991f5ddd4d82
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418216"
---
# <a name="imapiprovidershutdownqueryfastshutdown"></a>IMAPIProviderShutdown::QueryFastShutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
向 MAPI 提供程序查询快速关闭支持。 
  
```cpp
HRESULT QueryFastShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> MAPI 提供程序支持 MAPI 客户端执行快速关闭。
    
MAPI_E_NO_SUPPORT
  
> MAPI 提供程序不支持 MAPI 客户端执行快速关闭。
    
## <a name="remarks"></a>备注

无需支持客户端快速关闭的 MAPI 提供程序仍应实现 [IMAPIProviderShutdown](imapiprovidershutdowniunknown.md) 接口，并且让 **IMAPIProviderShutdown：：QueryFastShutdown** 方法返回 MAPI_E_NO_SUPPORT。 对于Outlook MAPI 客户端，这将导致Outlook等待所有外部引用在退出之前释放。 
  
根据用户的快速关闭Windows设置，不实现 **IMAPIProviderShutdown** 接口不一定阻止客户端快速关闭。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

