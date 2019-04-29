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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 32a0051207ae34f919523fbfe3e01601b7ea5d2a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408682"
---
# <a name="imapiclientshutdowndofastshutdown"></a>IMAPIClientShutdown::DoFastShutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示 MAPI 客户端在立即退出客户端进程的意图。
  
```cpp
HRESULT DoFastShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> mapi 子系统已向加载的 mapi 提供程序指明 mapi 客户端立即退出, 并且 mapi 提供程序已准备好进行客户端退出。
    
MAPI_E_NO_SUPPORT
  
> MAPI 子系统不支持客户端快速关闭。
    
## <a name="remarks"></a>说明

为了避免从 mapi 客户端的快速关闭中丢失数据, mapi 客户端应调用[IMAPIClientShutdown:: NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)和**IMAPIClientShutdown::D**基于 MAPI 子系统返回的 S_OK 结果的 ofastshutdown 方法[IMAPIClientShutdown:: QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法。 有关详细信息, 请参阅[Fast Shutdown 的最佳实践](best-practices-for-fast-shutdown.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

