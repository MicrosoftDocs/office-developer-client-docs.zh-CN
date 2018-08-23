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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 251359a98f89c88e707e4f705bd94b1f30b32cbd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592050"
---
# <a name="imapiprovidershutdownnotifyprocessshutdown"></a>IMAPIProviderShutdown::NotifyProcessShutdown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
表示的 MAPI 提供程序，MAPI 客户端将要执行快速关闭，以便提供程序可以执行操作，以防止数据丢失。
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> MAPI 提供程序采取操作来 MAPI 客户端关闭时防止数据丢失。
    
## <a name="see-also"></a>另请参阅



[IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

