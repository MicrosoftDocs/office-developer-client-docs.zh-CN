---
title: IMAPIWaitResult::End
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIWaitResult.End
api_type:
- COM
ms.assetid: 7463c9e8-d065-4cc3-ac01-d428b57bbc88
description: IMAPIWaitResult::End
Last modified: April 26, 2021
ms.openlocfilehash: 3432bf3b71fa7e15cb4621d461a8d4bbe962f1ba
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062030"
---
# <a name="imapiwaitresultend"></a>IMAPIWaitResult::End
  
**适用于：** Outlook 2013 |Outlook 2016 |2019

在此线程上启动 BLOCKING 调用，该调用将在指定的毫秒数已过或 MAPI 已初始化时返回。 INFINITE 可用于无限等待。

```cpp
HRESULT IMAPIWaitResult::End(DWORD timeout)
```

## <a name="parameters"></a>参数

_timeout_
> [in]等待 MAPI 初始化的毫秒数，可以传递 INFINITE (0xFFFFFFFF) 永久等待。

## <a name="return-value"></a>返回值

S_OK
> MAPI 已成功初始化

HRESULT_FROM_WIN32 (ERROR_TIMEOUT) 
> 当给定非无限超时时，这表示该期间未初始化 MAPI。

## <a name="remarks"></a>备注
此 API 的行为与 [IMAPInitMonitor：：Wait 完全相同](imapiinitmonitor-wait.md)。
  
## <a name="see-also"></a>另请参阅

[IMAPIInitMonitor::IsInitialized](imapiinitmonitor-isinitialized.md)

[IMAPIInitMonitor::BeginWait](imapiinitmonitor-beginwait.md)

[CreateMAPIInitializationMonitor](createmapiinitializationmonitor.md)

[IMAPIWaitResult](imapiwaitresultiunknown.md)
