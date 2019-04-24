---
title: IMAPIProviderShutdownNotifyProcessShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProviderShutdown.NotifyProcessShutdown
api_type:
- COM
ms.assetid: a00d71b1-d705-40d5-b667-f91b57db85da
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4b18cfc2191ffee936e1056d9bb656a7ad7dd3ec
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326388"
---
# <a name="imapiprovidershutdownnotifyprocessshutdown"></a>IMAPIProviderShutdown::NotifyProcessShutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
向 mapi 提供程序指示 mapi 客户端即将执行快速关闭, 以便提供程序可以采取措施来防止数据丢失。
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> mapi 提供程序在 mapi 客户端关闭时采取措施来防止数据丢失。
    
## <a name="see-also"></a>另请参阅



[IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

