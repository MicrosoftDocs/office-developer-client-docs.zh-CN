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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408206"
---
# <a name="mapideinitidle"></a><span data-ttu-id="faf64-103">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="faf64-103">MAPIDeInitIdle</span></span>

  
  
<span data-ttu-id="faf64-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="faf64-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="faf64-105">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="faf64-105">Shuts down the MAPI idle engine for the calling application.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="faf64-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="faf64-106">Header file:</span></span>  <br/> |<span data-ttu-id="faf64-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="faf64-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="faf64-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="faf64-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="faf64-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="faf64-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="faf64-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="faf64-110">Called by:</span></span>  <br/> |<span data-ttu-id="faf64-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="faf64-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void MAPIDeInitIdle( void );
```

## <a name="parameters"></a><span data-ttu-id="faf64-112">参数</span><span class="sxs-lookup"><span data-stu-id="faf64-112">Parameters</span></span>

<span data-ttu-id="faf64-113">无。</span><span class="sxs-lookup"><span data-stu-id="faf64-113">None.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="faf64-114">返回值</span><span class="sxs-lookup"><span data-stu-id="faf64-114">Return value</span></span>

<span data-ttu-id="faf64-115">无。</span><span class="sxs-lookup"><span data-stu-id="faf64-115">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="faf64-116">说明</span><span class="sxs-lookup"><span data-stu-id="faf64-116">Remarks</span></span>

<span data-ttu-id="faf64-117">客户端应用程序或服务提供商在不再需要空闲引擎（例如，即将停止处理）时，应调用 **MAPIDeInitIdle。**</span><span class="sxs-lookup"><span data-stu-id="faf64-117">A client application or service provider should call **MAPIDeInitIdle** when it no longer needs the idle engine, for example, when it is about to stop processing.</span></span> 
  
<span data-ttu-id="faf64-118">对 [MAPIInitIdle 的](mapiinitidle.md) 每次调用都必须与 **对 MAPIDeInitIdle** 的后续调用匹配，否则空闲引擎将保持为调用应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="faf64-118">Every call to [MAPIInitIdle](mapiinitidle.md) must be matched by a subsequent call to **MAPIDeInitIdle**, or the idle engine is left running for the calling application.</span></span> 
  
<span data-ttu-id="faf64-119">以下函数基于 [FNIDLE](fnidle.md) 函数原型处理 MAPI 空闲引擎和空闲例程：</span><span class="sxs-lookup"><span data-stu-id="faf64-119">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="faf64-120">**空闲例程函数**</span><span class="sxs-lookup"><span data-stu-id="faf64-120">**Idle routine function**</span></span>|<span data-ttu-id="faf64-121">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="faf64-121">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="faf64-122">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="faf64-122">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="faf64-123">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="faf64-123">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="faf64-124">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="faf64-124">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="faf64-125">从 MAPI 系统中删除注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="faf64-125">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="faf64-126">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="faf64-126">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="faf64-127">禁用或重新启用注册的空闲例程，而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="faf64-127">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="faf64-128">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="faf64-128">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="faf64-129">将空闲例程添加到 MAPI 系统，启用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="faf64-129">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|<span data-ttu-id="faf64-130">**MAPIDeInitIdle**</span><span class="sxs-lookup"><span data-stu-id="faf64-130">**MAPIDeInitIdle**</span></span> <br/> |<span data-ttu-id="faf64-131">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="faf64-131">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="faf64-132">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="faf64-132">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="faf64-133">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="faf64-133">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="faf64-134">当平台的所有前台任务变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="faf64-134">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="faf64-135">无法保证在优先级相同的空闲例程之间调用顺序。</span><span class="sxs-lookup"><span data-stu-id="faf64-135">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

