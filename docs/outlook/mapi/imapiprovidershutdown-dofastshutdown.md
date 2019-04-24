---
title: IMAPIProviderShutdownDoFastShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProviderShutdown.DoFastShutdown
api_type:
- COM
ms.assetid: d2b66a8e-2e28-4c32-af95-38d345c7bbd7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4ff93ed9353d58ef6b68823bebf8b5b27a0df6e8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322419"
---
# <a name="imapiprovidershutdowndofastshutdown"></a>IMAPIProviderShutdown::DoFastShutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
向 mapi 提供程序指示 mapi 客户端立即退出, 以便 mapi 提供程序将保留所做的更改以防止数据丢失。
  
```cpp
HRESULT DoFastShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> mapi 提供程序已准备好, 可立即退出 mapi 客户端。 
    
## <a name="see-also"></a>另请参阅



[IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

