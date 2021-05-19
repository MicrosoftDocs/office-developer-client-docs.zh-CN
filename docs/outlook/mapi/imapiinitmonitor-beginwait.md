---
title: imapiinitmonitor-beginwait
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIINITMONITOR.BeginWait
api_type:
- COM
ms.assetid: 71f565a9-651c-42b5-9102-91b728b681ae
description: IMAPIInitMonitor：：BeginWait"
Last modified: April 26, 2021
ms.openlocfilehash: 43a88507cbfc23b3b842f51e69eb4bd791bcfda8
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062016"
---
# <a name="imapiinitmonitorbeginwait"></a>IMAPIInitMonitor::BeginWait
  
**适用于：** Outlook 2016 |2019
  
开始等待 MAPI 初始化或经过的指定毫秒数。 这将返回 IMAPIWaitResult 接口，该接口应调用 **IMAPIWaitResult：：End** 以启动等待。 这允许调用方控制我们在等待时被阻止的线程。

```cpp
HRESULT IMAPIInitMonitor::BeginWait(DWORD timeout, IMAPIWaitResult** ppResult)
```

## <a name="parameters"></a>参数
_timeout_
>[in]等待 MAPI 初始化的毫秒数，可以设置为 INFINITE 以永久等待初始化发生。

_ppResult_
>[out]用于接收新创建的等待接口的指针。

## <a name="return-value"></a>返回值
S_OK
>已成功启动等待操作。

E_OUTOFMEMORY
>没有足够的内存创建新对象

## <a name="remarks"></a>备注
此 API 为调用方提供了一个 (接口，该接口是线程) ，可用于启动阻止等待 MAPI 初始化。 这使使用者能够确定等待其应用程序的最佳等待时间。   调用 IMAPIWaitResult：：End 的行为与调用 IMAPIInitMonitor：：Wait 的行为相同。

## <a name="see-also"></a>另请参阅

[IMAPIInitMonitor](imapiinitmonitoriunknown.md)

[IMAPIInitMonitor::IsInitialized](imapiinitmonitor-isinitialized.md)

[IMAPIInitMonitor::Wait](imapiinitmonitor-wait.md)

[CreateMAPIInitializationMonitor](createmapiinitializationmonitor.md)

[IMAPIWaitResult](imapiwaitresultiunknown.md)
