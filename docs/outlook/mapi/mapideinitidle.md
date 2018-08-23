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
ms.openlocfilehash: 33f4634623662b7bc09e0830e8bd0b51adc7799d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583496"
---
# <a name="mapideinitidle"></a><span data-ttu-id="b9bd4-103">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="b9bd4-103">MAPIDeInitIdle</span></span>

  
  
<span data-ttu-id="b9bd4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9bd4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b9bd4-105">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-105">Shuts down the MAPI idle engine for the calling application.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b9bd4-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b9bd4-106">Header file:</span></span>  <br/> |<span data-ttu-id="b9bd4-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="b9bd4-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="b9bd4-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="b9bd4-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="b9bd4-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="b9bd4-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="b9bd4-110">调用：</span><span class="sxs-lookup"><span data-stu-id="b9bd4-110">Called by:</span></span>  <br/> |<span data-ttu-id="b9bd4-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="b9bd4-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void MAPIDeInitIdle( void );
```

## <a name="parameters"></a><span data-ttu-id="b9bd4-112">参数</span><span class="sxs-lookup"><span data-stu-id="b9bd4-112">Parameters</span></span>

<span data-ttu-id="b9bd4-113">无。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-113">None.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="b9bd4-114">返回值</span><span class="sxs-lookup"><span data-stu-id="b9bd4-114">Return value</span></span>

<span data-ttu-id="b9bd4-115">无。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-115">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b9bd4-116">注解</span><span class="sxs-lookup"><span data-stu-id="b9bd4-116">Remarks</span></span>

<span data-ttu-id="b9bd4-117">客户端应用程序或服务提供商应**MAPIDeInitIdle**需要时调用不再空闲引擎，例如，当要停止处理。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-117">A client application or service provider should call **MAPIDeInitIdle** when it no longer needs the idle engine, for example, when it is about to stop processing.</span></span> 
  
<span data-ttu-id="b9bd4-118">每次调用[MAPIInitIdle](mapiinitidle.md)必须匹配通过后续调用**MAPIDeInitIdle**，或空闲引擎仍在运行调用应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-118">Every call to [MAPIInitIdle](mapiinitidle.md) must be matched by a subsequent call to **MAPIDeInitIdle**, or the idle engine is left running for the calling application.</span></span> 
  
<span data-ttu-id="b9bd4-119">下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程：</span><span class="sxs-lookup"><span data-stu-id="b9bd4-119">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="b9bd4-120">**空闲例行函数**</span><span class="sxs-lookup"><span data-stu-id="b9bd4-120">**Idle routine function**</span></span>|<span data-ttu-id="b9bd4-121">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="b9bd4-121">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b9bd4-122">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b9bd4-122">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="b9bd4-123">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-123">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="b9bd4-124">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b9bd4-124">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="b9bd4-125">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-125">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="b9bd4-126">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b9bd4-126">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="b9bd4-127">禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-127">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="b9bd4-128">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b9bd4-128">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="b9bd4-129">将一个空闲例程添加到 MAPI 系统，使用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-129">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|<span data-ttu-id="b9bd4-130">**MAPIDeInitIdle**</span><span class="sxs-lookup"><span data-stu-id="b9bd4-130">**MAPIDeInitIdle**</span></span> <br/> |<span data-ttu-id="b9bd4-131">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-131">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="b9bd4-132">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="b9bd4-132">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="b9bd4-133">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-133">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="b9bd4-134">当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-134">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="b9bd4-135">不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。</span><span class="sxs-lookup"><span data-stu-id="b9bd4-135">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

