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
  
指示 MAPI 客户端打算立即退出客户端进程。
  
```cpp
HRESULT DoFastShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> MAPI 子系统向已加载的 MAPI 提供程序指示 MAPI 客户端正在立即退出，并且 MAPI 提供程序已准备好退出客户端。
    
MAPI_E_NO_SUPPORT
  
> MAPI 子系统不支持客户端快速关闭。
    
## <a name="remarks"></a>备注

为了避免由于快速关闭 MAPI 客户端而丢失数据，MAPI 客户端应基于 [IMAPIClientShutdown：：QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法中 MAPI 子系统返回的 S_OK 结果调用 [IMAPIClientShutdown：：NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)和 **IMAPIClientShutdown：:D oFastShutdown** 方法。 有关详细信息，请参阅[Best Practices for Fast Shutdown。](best-practices-for-fast-shutdown.md)
  
## <a name="see-also"></a>另请参阅



[IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

