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
# <a name="enableidleroutine"></a><span data-ttu-id="cb524-103">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="cb524-103">EnableIdleRoutine</span></span>

  
  
<span data-ttu-id="cb524-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cb524-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cb524-105">启用或禁用基于 [FNIDLE](fnidle.md) 的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="cb524-105">Enables or disables a [FNIDLE](fnidle.md) based idle routine.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cb524-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="cb524-106">Header file:</span></span>  <br/> |<span data-ttu-id="cb524-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="cb524-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="cb524-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="cb524-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="cb524-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="cb524-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="cb524-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="cb524-110">Called by:</span></span>  <br/> |<span data-ttu-id="cb524-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="cb524-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID EnableIdleRoutine(
  FTG ftg,
  BOOL fEnable
);
```

## <a name="parameters"></a><span data-ttu-id="cb524-112">参数</span><span class="sxs-lookup"><span data-stu-id="cb524-112">Parameters</span></span>

 <span data-ttu-id="cb524-113">_ftg_</span><span class="sxs-lookup"><span data-stu-id="cb524-113">_ftg_</span></span>
  
> <span data-ttu-id="cb524-114">[in]标识要启用或禁用的空闲例程的函数标记。</span><span class="sxs-lookup"><span data-stu-id="cb524-114">[in] Function tag that identifies the idle routine to be enabled or disabled.</span></span> 
    
 <span data-ttu-id="cb524-115">_fEnable_</span><span class="sxs-lookup"><span data-stu-id="cb524-115">_fEnable_</span></span>
  
> <span data-ttu-id="cb524-116">[in]如果空闲引擎应启用空闲例程，则包含 TRUE;如果应禁用该例程，则包含 FALSE。</span><span class="sxs-lookup"><span data-stu-id="cb524-116">[in] Contains TRUE if the idle engine should enable the idle routine, or FALSE if it should disable it.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cb524-117">返回值</span><span class="sxs-lookup"><span data-stu-id="cb524-117">Return value</span></span>

<span data-ttu-id="cb524-118">无。</span><span class="sxs-lookup"><span data-stu-id="cb524-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cb524-119">说明</span><span class="sxs-lookup"><span data-stu-id="cb524-119">Remarks</span></span>

<span data-ttu-id="cb524-120">以下函数基于 [FNIDLE](fnidle.md) 函数原型处理 MAPI 空闲引擎和空闲例程：</span><span class="sxs-lookup"><span data-stu-id="cb524-120">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="cb524-121">**空闲例程函数**</span><span class="sxs-lookup"><span data-stu-id="cb524-121">**Idle routine function**</span></span>|<span data-ttu-id="cb524-122">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="cb524-122">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="cb524-123">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="cb524-123">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="cb524-124">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="cb524-124">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="cb524-125">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="cb524-125">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="cb524-126">从 MAPI 系统中删除注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="cb524-126">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|<span data-ttu-id="cb524-127">**EnableIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="cb524-127">**EnableIdleRoutine**</span></span> <br/> |<span data-ttu-id="cb524-128">禁用或重新启用注册的空闲例程，而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="cb524-128">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="cb524-129">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="cb524-129">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="cb524-130">将空闲例程添加到 MAPI 系统，启用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="cb524-130">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="cb524-131">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="cb524-131">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="cb524-132">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="cb524-132">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="cb524-133">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="cb524-133">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="cb524-134">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="cb524-134">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
 <span data-ttu-id="cb524-135">ChangeIdleRoutine、DeregisterIdleRoutine 和 **EnableIdleRoutine** 将 **FtgRegisterIdleRoutine** 返回的函数标记作为输入参数。 </span><span class="sxs-lookup"><span data-stu-id="cb524-135">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="cb524-136">当平台的所有前台任务变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="cb524-136">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="cb524-137">无法保证在优先级相同的空闲例程之间调用顺序。</span><span class="sxs-lookup"><span data-stu-id="cb524-137">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

