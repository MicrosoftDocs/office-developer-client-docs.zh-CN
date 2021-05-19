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
# <a name="imapiinitmonitorisinitialized"></a><span data-ttu-id="09163-103">IMAPIInitMonitor::IsInitialized</span><span class="sxs-lookup"><span data-stu-id="09163-103">IMAPIInitMonitor::IsInitialized</span></span>
  
<span data-ttu-id="09163-104">**适用于：** Outlook 2013 |Outlook 2016 |2019</span><span class="sxs-lookup"><span data-stu-id="09163-104">**Applies to**: Outlook 2013 | Outlook 2016 | 2019</span></span>
  
<span data-ttu-id="09163-105">查询 MAPI 以确定它当前是否正在调用过程中初始化。</span><span class="sxs-lookup"><span data-stu-id="09163-105">Queries MAPI to determine if it currently initialized in the calling process.</span></span>

```cpp
BOOL IMAPIInitMonitor::IsInitialized()  
```

## <a name="parameters"></a><span data-ttu-id="09163-106">参数</span><span class="sxs-lookup"><span data-stu-id="09163-106">Parameters</span></span>
<span data-ttu-id="09163-107">无</span><span class="sxs-lookup"><span data-stu-id="09163-107">None</span></span>

## <a name="return-value"></a><span data-ttu-id="09163-108">返回值</span><span class="sxs-lookup"><span data-stu-id="09163-108">Return value</span></span>
<span data-ttu-id="09163-109">指示 MAPI 初始化的当前状态 BOOL，值为 TRUE 表示 MAPI 已初始化且可供使用，而 FALSE 值表示 MAPI 当前未初始化，尚未准备好使用。</span><span class="sxs-lookup"><span data-stu-id="09163-109">A BOOL indicating the current state of MAPI initialization, a value of TRUE means MAPI has been initialized and is available for use, while a value of FALSE means MAPI is currenty uninitialized and is not ready be consumed.</span></span>

## <a name="remarks"></a><span data-ttu-id="09163-110">备注</span><span class="sxs-lookup"><span data-stu-id="09163-110">Remarks</span></span>
<span data-ttu-id="09163-111">这可用于确定 MAPI 是否可供使用，例如，如果应用程序仅在 MAPI 已初始化时要执行某些操作，这可能在后台任务中是一个有用的检查，可以防止使 MAPI 因可选工作而旋转的成本。</span><span class="sxs-lookup"><span data-stu-id="09163-111">This can be used to determine if MAPI is ready to be used, for example, if your application wanted to do something only if MAPI has already be initialized, this could be a useful check in a background task to prevent the cost of spinning up MAPI for optional work.</span></span>

## <a name="see-also"></a><span data-ttu-id="09163-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09163-112">See also</span></span>

[<span data-ttu-id="09163-113">IMAPIInitMonitor::Wait</span><span class="sxs-lookup"><span data-stu-id="09163-113">IMAPIInitMonitor::Wait</span></span>](imapiinitmonitor-wait.md)

[<span data-ttu-id="09163-114">CreateMAPIInitializationMonitor</span><span class="sxs-lookup"><span data-stu-id="09163-114">CreateMAPIInitializationMonitor</span></span>](createmapiinitializationmonitor.md)
