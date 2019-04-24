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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351357"
---
# <a name="imapiclientshutdownnotifyprocessshutdown"></a>IMAPIClientShutdown::NotifyProcessShutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示 MAPI 客户端的意向继续关闭。
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> mapi 子系统已尝试通知加载的 mapi 提供程序, mapi 客户端即将执行快速关闭。
    
## <a name="remarks"></a>注解

为了避免从 mapi 客户端的快速关闭中丢失数据, mapi 客户端应调用**IMAPIClientShutdown:: NotifyProcessShutdown**和[IMAPIClientShutdown::D](imapiclientshutdown-dofastshutdown.md)基于 MAPI 子系统返回的 S_OK 结果的 ofastshutdown 方法[IMAPIClientShutdown:: QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法。 有关详细信息, 请参阅[Fast Shutdown 的最佳实践](best-practices-for-fast-shutdown.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

