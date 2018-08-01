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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 04a9b631c3a4f33282bce44e06d92e089349c76b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775307"
---
# <a name="imapiclientshutdownnotifyprocessshutdown"></a>IMAPIClientShutdown::NotifyProcessShutdown

  
  
**适用于**： Outlook 
  
表示的 MAPI 客户端的目的，继续执行关闭。
  
```cpp
HRESULT NotifyProcessShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> MAPI 子系统试图通知 MAPI 客户端正在进行快速关闭加载的 MAPI 提供程序。
    
## <a name="remarks"></a>说明

若要避免从 MAPI 客户端快速关闭数据丢失，MAPI 客户端应调用基于 MAPI 子系统中返回 S_OK 结果的**IMAPIClientShutdown::NotifyProcessShutdown**和[IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md)方法[IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法中。 有关详细信息，请参阅[Fast 关闭的最佳实践](best-practices-for-fast-shutdown.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

