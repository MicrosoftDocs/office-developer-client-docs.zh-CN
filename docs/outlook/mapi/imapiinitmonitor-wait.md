---
title: imapiinitmonitor-wait
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIINITMONITOR.Wait
api_type:
- COM
ms.assetid: ed566cae-35a2-4716-817b-54d1ba6825c6
description: IMAPIAMonitor：：Wait
Last modified: April 26, 2021
ms.openlocfilehash: ee46a2744e67804c9dfdac8d7512db1d7b07f8ba
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062009"
---
# <a name="imapiinitmonitorwait"></a>IMAPIInitMonitor::Wait
  
**适用于：** Outlook 2013 |Outlook 2016 |2019
  
在此线程上启动 BLOCKING 调用，该调用将在指定的毫秒数已过或 MAPI 已初始化时返回。 INFINITE 可用于无限等待。

```cpp
HRESULT IMAPIInitMonitor::Wait(DWORD timeout)
```

## <a name="parameters"></a>参数
_timeout_
> [in]等待 MAPI 初始化的毫秒数，可以传递 INFINITE (0xFFFFFFFF) 永久等待。

## <a name="return-value"></a>返回值

S_OK
> MAPI 已成功初始化。

HRESULT_FROM_WIN32 (ERROR_TIMEOUT) 
> 当给定非无限超时时，这表示该期间未初始化 MAPI。

## <a name="remarks"></a>备注
  
## <a name="see-also"></a>另请参阅

[IMAPIInitMonitor](imapiinitmonitoriunknown.md)

[IMAPIInitMonitor::IsInitialized](imapiinitmonitor-isinitialized.md)

[IMAPIInitMonitor::BeginWait](imapiinitmonitor-beginwait.md)

[CreateMAPIInitializationMonitor](createmapiinitializationmonitor.md)

[IMAPIWaitResult](imapiwaitresultiunknown.md)
