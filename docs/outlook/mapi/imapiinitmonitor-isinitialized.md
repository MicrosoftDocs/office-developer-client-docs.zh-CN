---
title: imapiinitmonitor-isinitialized
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIINITMONITOR.IsInitialized
api_type:
- COM
ms.assetid: 1af0bf93-6bcb-4235-ac30-0d00245ec636
description: IMAPIInitMonitor::IsInitialized
Last modified: April 26, 2021
ms.openlocfilehash: 6870c8fa0de51b626662c58b2c8c300c3a4d806e
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062023"
---
# <a name="imapiinitmonitorisinitialized"></a>IMAPIInitMonitor::IsInitialized
  
**适用于：** Outlook 2013 |Outlook 2016 |2019
  
查询 MAPI 以确定它当前是否正在调用过程中初始化。

```cpp
BOOL IMAPIInitMonitor::IsInitialized()  
```

## <a name="parameters"></a>参数
无

## <a name="return-value"></a>返回值
指示 MAPI 初始化的当前状态 BOOL，值为 TRUE 表示 MAPI 已初始化且可供使用，而 FALSE 值表示 MAPI 当前未初始化，尚未准备好使用。

## <a name="remarks"></a>备注
这可用于确定 MAPI 是否可供使用，例如，如果应用程序仅在 MAPI 已初始化时要执行某些操作，这可能在后台任务中是一个有用的检查，可以防止使 MAPI 因可选工作而旋转的成本。

## <a name="see-also"></a>另请参阅

[IMAPIInitMonitor::Wait](imapiinitmonitor-wait.md)

[CreateMAPIInitializationMonitor](createmapiinitializationmonitor.md)
