---
title: IMAPIClientShutdownDoFastShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIClientShutdown.DoFastShutdown
api_type:
- COM
ms.assetid: 310cba9a-a343-484d-a029-fcd51b731460
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 41c4ee65ce6ae8f2e0d978f1e2bd95adb4f5872a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575173"
---
# <a name="imapiclientshutdowndofastshutdown"></a>IMAPIClientShutdown::DoFastShutdown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示的 MAPI 客户端的目的立即退出该客户端进程。
  
```cpp
HRESULT DoFastShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> 立即退出 MAPI 客户端和 MAPI 提供程序可供客户端退出 MAPI 子系统表示到加载 MAPI 提供程序。
    
MAPI_E_NO_SUPPORT
  
> MAPI 子系统不支持客户端快速关闭。
    
## <a name="remarks"></a>注解

若要避免从 MAPI 客户端快速关闭数据丢失，MAPI 客户端应调用基于 MAPI 子系统中返回 S_OK 结果的[IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)和**IMAPIClientShutdown::DoFastShutdown**方法[IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法中。 有关详细信息，请参阅[Fast 关闭的最佳实践](best-practices-for-fast-shutdown.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

