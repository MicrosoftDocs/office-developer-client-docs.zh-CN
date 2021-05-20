---
title: IMAPIClientShutdownNotifyProcessShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIClientShutdown.NotifyProcessShutdown
api_type:
- COM
ms.assetid: 42dd7889-5e00-419a-91e7-8350be4efd35
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6eef3047368caca5bd932e19738b1d996c3ff28a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438867"
---
# <a name="imapiclientshutdownnotifyprocessshutdown"></a>IMAPIClientShutdown::NotifyProcessShutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示 MAPI 客户端继续关闭的意图。
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> MAPI 子系统已尝试通知已加载的 MAPI 提供程序 MAPI 客户端将执行快速关闭。
    
## <a name="remarks"></a>备注

为了避免由于快速关闭 MAPI 客户端而丢失数据，MAPI 客户端应基于 [IMAPIClientShutdown：：QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法中 MAPI 子系统返回的 S_OK 结果调用 **IMAPIClientShutdown：：NotifyProcessShutdown** 和 [IMAPIClientShutdown：:D oFastShutdown](imapiclientshutdown-dofastshutdown.md)方法。 有关详细信息，请参阅[Best Practices for Fast Shutdown。](best-practices-for-fast-shutdown.md)
  
## <a name="see-also"></a>另请参阅



[IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

