---
title: EnableIdleRoutine
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.EnableIdleRoutine
api_type:
- COM
ms.assetid: 332ea831-bdf9-4dbd-b9c7-a80f8ba11b3b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e04c872762665f4b3a22559dc2ed1504e7b8f9af
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410219"
---
# <a name="enableidleroutine"></a><span data-ttu-id="bad2d-103">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="bad2d-103">EnableIdleRoutine</span></span>

  
  
<span data-ttu-id="bad2d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bad2d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bad2d-105">启用或禁用基于[FNIDLE](fnidle.md)的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="bad2d-105">Enables or disables a [FNIDLE](fnidle.md) based idle routine.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bad2d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="bad2d-106">Header file:</span></span>  <br/> |<span data-ttu-id="bad2d-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="bad2d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="bad2d-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="bad2d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="bad2d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="bad2d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="bad2d-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="bad2d-110">Called by:</span></span>  <br/> |<span data-ttu-id="bad2d-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="bad2d-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID EnableIdleRoutine(
  FTG ftg,
  BOOL fEnable
);
```

## <a name="parameters"></a><span data-ttu-id="bad2d-112">参数</span><span class="sxs-lookup"><span data-stu-id="bad2d-112">Parameters</span></span>

 <span data-ttu-id="bad2d-113">_ftg_</span><span class="sxs-lookup"><span data-stu-id="bad2d-113">_ftg_</span></span>
  
> <span data-ttu-id="bad2d-114">实时用于标识要启用或禁用的空闲例程的 Function 标记。</span><span class="sxs-lookup"><span data-stu-id="bad2d-114">[in] Function tag that identifies the idle routine to be enabled or disabled.</span></span> 
    
 <span data-ttu-id="bad2d-115">_fEnable_</span><span class="sxs-lookup"><span data-stu-id="bad2d-115">_fEnable_</span></span>
  
> <span data-ttu-id="bad2d-116">实时如果空闲引擎应启用空闲例程, 则为 TRUE, 否则为 FALSE (如果它应禁用)。</span><span class="sxs-lookup"><span data-stu-id="bad2d-116">[in] Contains TRUE if the idle engine should enable the idle routine, or FALSE if it should disable it.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bad2d-117">返回值</span><span class="sxs-lookup"><span data-stu-id="bad2d-117">Return value</span></span>

<span data-ttu-id="bad2d-118">无。</span><span class="sxs-lookup"><span data-stu-id="bad2d-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="bad2d-119">说明</span><span class="sxs-lookup"><span data-stu-id="bad2d-119">Remarks</span></span>

<span data-ttu-id="bad2d-120">以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程:</span><span class="sxs-lookup"><span data-stu-id="bad2d-120">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="bad2d-121">**Idle 例程函数**</span><span class="sxs-lookup"><span data-stu-id="bad2d-121">**Idle routine function**</span></span>|<span data-ttu-id="bad2d-122">**使用**</span><span class="sxs-lookup"><span data-stu-id="bad2d-122">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="bad2d-123">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="bad2d-123">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="bad2d-124">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="bad2d-124">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="bad2d-125">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="bad2d-125">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="bad2d-126">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="bad2d-126">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|<span data-ttu-id="bad2d-127">**EnableIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="bad2d-127">**EnableIdleRoutine**</span></span> <br/> |<span data-ttu-id="bad2d-128">禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="bad2d-128">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="bad2d-129">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="bad2d-129">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="bad2d-130">将空闲例程添加到 MAPI 系统中 (无论是否启用)。</span><span class="sxs-lookup"><span data-stu-id="bad2d-130">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="bad2d-131">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="bad2d-131">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="bad2d-132">关闭呼叫应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="bad2d-132">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="bad2d-133">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="bad2d-133">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="bad2d-134">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="bad2d-134">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
 <span data-ttu-id="bad2d-135">**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**采用**FtgRegisterIdleRoutine**返回的函数标记作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="bad2d-135">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="bad2d-136">当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="bad2d-136">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="bad2d-137">在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。</span><span class="sxs-lookup"><span data-stu-id="bad2d-137">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

