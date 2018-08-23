---
title: IMAPIForm IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm
api_type:
- COM
ms.assetid: e9059739-51b4-4574-bd0f-709eb5144ae7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ce0e109aad52bfc4d7f4f55abfe1001d76276f64
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587129"
---
# <a name="imapiform--iunknown"></a><span data-ttu-id="4a3ac-103">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4a3ac-103">IMAPIForm : IUnknown</span></span>

  
  
<span data-ttu-id="4a3ac-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a3ac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a3ac-105">启用表单查看器处理窗体视图上下文和窗体通知，来执行窗体动词和关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="4a3ac-105">Enables form viewers to work with form view contexts and form notification, to perform form verbs, and to shut down forms.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4a3ac-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="4a3ac-106">Header file:</span></span>  <br/> |<span data-ttu-id="4a3ac-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="4a3ac-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="4a3ac-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="4a3ac-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="4a3ac-109">窗体对象</span><span class="sxs-lookup"><span data-stu-id="4a3ac-109">Form objects</span></span>  <br/> |
|<span data-ttu-id="4a3ac-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="4a3ac-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="4a3ac-111">表单服务器</span><span class="sxs-lookup"><span data-stu-id="4a3ac-111">Form servers</span></span>  <br/> |
|<span data-ttu-id="4a3ac-112">调用：</span><span class="sxs-lookup"><span data-stu-id="4a3ac-112">Called by:</span></span>  <br/> |<span data-ttu-id="4a3ac-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="4a3ac-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="4a3ac-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="4a3ac-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="4a3ac-115">IID_IMAPIForm</span><span class="sxs-lookup"><span data-stu-id="4a3ac-115">IID_IMAPIForm</span></span>  <br/> |
|<span data-ttu-id="4a3ac-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="4a3ac-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="4a3ac-117">LPMAPIFORM</span><span class="sxs-lookup"><span data-stu-id="4a3ac-117">LPMAPIFORM</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="4a3ac-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="4a3ac-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="4a3ac-119">SetViewContext</span><span class="sxs-lookup"><span data-stu-id="4a3ac-119">SetViewContext</span></span>](imapiform-setviewcontext.md) <br/> |<span data-ttu-id="4a3ac-120">建立窗体视图上下文。</span><span class="sxs-lookup"><span data-stu-id="4a3ac-120">Establishes a view context for the form.</span></span>  <br/> |
|[<span data-ttu-id="4a3ac-121">GetViewContext</span><span class="sxs-lookup"><span data-stu-id="4a3ac-121">GetViewContext</span></span>](imapiform-getviewcontext.md) <br/> |<span data-ttu-id="4a3ac-122">返回表单的当前视图上下文。</span><span class="sxs-lookup"><span data-stu-id="4a3ac-122">Returns the current view context for the form.</span></span>  <br/> |
|[<span data-ttu-id="4a3ac-123">ShutdownForm</span><span class="sxs-lookup"><span data-stu-id="4a3ac-123">ShutdownForm</span></span>](imapiform-shutdownform.md) <br/> |<span data-ttu-id="4a3ac-124">关闭表单。</span><span class="sxs-lookup"><span data-stu-id="4a3ac-124">Closes the form.</span></span>  <br/> |
|[<span data-ttu-id="4a3ac-125">DoVerb</span><span class="sxs-lookup"><span data-stu-id="4a3ac-125">DoVerb</span></span>](imapiform-doverb.md) <br/> |<span data-ttu-id="4a3ac-126">请求窗体执行任何任务它将与特定动词。</span><span class="sxs-lookup"><span data-stu-id="4a3ac-126">Requests that the form perform whatever tasks it associates with a specific verb.</span></span>  <br/> |
|[<span data-ttu-id="4a3ac-127">建议</span><span class="sxs-lookup"><span data-stu-id="4a3ac-127">Advise</span></span>](imapiform-advise.md) <br/> |<span data-ttu-id="4a3ac-128">注册的窗体查看有关影响窗体的事件通知。</span><span class="sxs-lookup"><span data-stu-id="4a3ac-128">Registers a form viewer for notifications about events that affect the form.</span></span>  <br/> |
|[<span data-ttu-id="4a3ac-129">取消通知</span><span class="sxs-lookup"><span data-stu-id="4a3ac-129">Unadvise</span></span>](imapiform-unadvise.md) <br/> |<span data-ttu-id="4a3ac-130">使用窗体查看器通过调用**Advise**以前建立取消通知注册。</span><span class="sxs-lookup"><span data-stu-id="4a3ac-130">Cancels a registration for notifications with a form viewer previously established by calling **Advise**.</span></span>  <br/> |
|[<span data-ttu-id="4a3ac-131">时出错</span><span class="sxs-lookup"><span data-stu-id="4a3ac-131">GetLastError</span></span>](imapiform-getlasterror.md) <br/> |<span data-ttu-id="4a3ac-132">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的 form 对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="4a3ac-132">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the form object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4a3ac-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a3ac-133">See also</span></span>



[<span data-ttu-id="4a3ac-134">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="4a3ac-134">MAPI Interfaces</span></span>](mapi-interfaces.md)

