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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4301fb504439cf0ebd70b5ece589c812cb74844e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585295"
---
# <a name="imapiprovidershutdownqueryfastshutdown"></a>IMAPIProviderShutdown::QueryFastShutdown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
查询快速关闭 MAPI 提供程序支持。 
  
```cpp
HRESULT QueryFastShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> MAPI 提供程序支持 MAPI 客户端执行快速关闭。
    
MAPI_E_NO_SUPPORT
  
> MAPI 提供程序不支持 MAPI 客户端执行快速关闭。
    
## <a name="remarks"></a>注解

MAPI 提供程序不需要支持客户端快速关闭仍应实现[IMAPIProviderShutdown](imapiprovidershutdowniunknown.md)接口，并让 MAPI_E_NO_SUPPORT **IMAPIProviderShutdown::QueryFastShutdown**方法。 对于作为 MAPI 客户端的 Outlook，这会导致 Outlook 等待它退出之前，必须释放的所有外部引用。 
  
根据用户的 Windows 注册表设置的快速关闭不实现**IMAPIProviderShutdown**接口不一定是阻止客户端快速关闭。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

