---
title: MAPIDeInitIdle
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIDeInitIdle
api_type:
- COM
ms.assetid: f7b04486-bc48-4ba4-9f35-f021e06124bf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 74bba3ea9982838f0d010bbf106c1132df1c2c25
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357321"
---
# <a name="mapideinitidle"></a><span data-ttu-id="f2a03-103">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="f2a03-103">MAPIDeInitIdle</span></span>

  
  
<span data-ttu-id="f2a03-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f2a03-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f2a03-105">关闭呼叫应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="f2a03-105">Shuts down the MAPI idle engine for the calling application.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f2a03-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f2a03-106">Header file:</span></span>  <br/> |<span data-ttu-id="f2a03-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="f2a03-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="f2a03-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="f2a03-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f2a03-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f2a03-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f2a03-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="f2a03-110">Called by:</span></span>  <br/> |<span data-ttu-id="f2a03-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="f2a03-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void MAPIDeInitIdle( void );
```

## <a name="parameters"></a><span data-ttu-id="f2a03-112">参数</span><span class="sxs-lookup"><span data-stu-id="f2a03-112">Parameters</span></span>

<span data-ttu-id="f2a03-113">无。</span><span class="sxs-lookup"><span data-stu-id="f2a03-113">None.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="f2a03-114">返回值</span><span class="sxs-lookup"><span data-stu-id="f2a03-114">Return value</span></span>

<span data-ttu-id="f2a03-115">无。</span><span class="sxs-lookup"><span data-stu-id="f2a03-115">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f2a03-116">注解</span><span class="sxs-lookup"><span data-stu-id="f2a03-116">Remarks</span></span>

<span data-ttu-id="f2a03-117">客户端应用程序或服务提供商应在不再需要空闲引擎时调用**MAPIDeInitIdle** , 例如, 当即将停止处理时。</span><span class="sxs-lookup"><span data-stu-id="f2a03-117">A client application or service provider should call **MAPIDeInitIdle** when it no longer needs the idle engine, for example, when it is about to stop processing.</span></span> 
  
<span data-ttu-id="f2a03-118">每次调用[MAPIInitIdle](mapiinitidle.md)时, 都必须通过对**MAPIDeInitIdle**的后续调用进行匹配, 否则会为调用应用程序保持空闲引擎的运行状态。</span><span class="sxs-lookup"><span data-stu-id="f2a03-118">Every call to [MAPIInitIdle](mapiinitidle.md) must be matched by a subsequent call to **MAPIDeInitIdle**, or the idle engine is left running for the calling application.</span></span> 
  
<span data-ttu-id="f2a03-119">以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程:</span><span class="sxs-lookup"><span data-stu-id="f2a03-119">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="f2a03-120">**Idle 例程函数**</span><span class="sxs-lookup"><span data-stu-id="f2a03-120">**Idle routine function**</span></span>|<span data-ttu-id="f2a03-121">**使用**</span><span class="sxs-lookup"><span data-stu-id="f2a03-121">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f2a03-122">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="f2a03-122">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="f2a03-123">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="f2a03-123">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="f2a03-124">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="f2a03-124">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="f2a03-125">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="f2a03-125">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="f2a03-126">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="f2a03-126">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="f2a03-127">禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="f2a03-127">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="f2a03-128">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="f2a03-128">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="f2a03-129">将空闲例程添加到 MAPI 系统中 (无论是否启用)。</span><span class="sxs-lookup"><span data-stu-id="f2a03-129">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|<span data-ttu-id="f2a03-130">**MAPIDeInitIdle**</span><span class="sxs-lookup"><span data-stu-id="f2a03-130">**MAPIDeInitIdle**</span></span> <br/> |<span data-ttu-id="f2a03-131">关闭呼叫应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="f2a03-131">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="f2a03-132">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="f2a03-132">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="f2a03-133">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="f2a03-133">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="f2a03-134">当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="f2a03-134">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="f2a03-135">在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。</span><span class="sxs-lookup"><span data-stu-id="f2a03-135">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

