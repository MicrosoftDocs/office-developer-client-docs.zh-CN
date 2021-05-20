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
ms.openlocfilehash: 172cbf9478d3206742df61d211051594e69ab173
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436382"
---
# <a name="imapiform--iunknown"></a><span data-ttu-id="aa0ea-103">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="aa0ea-103">IMAPIForm : IUnknown</span></span>

  
  
<span data-ttu-id="aa0ea-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa0ea-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa0ea-105">允许表单查看器使用表单视图上下文和表单通知、执行表单谓词和关闭表单。</span><span class="sxs-lookup"><span data-stu-id="aa0ea-105">Enables form viewers to work with form view contexts and form notification, to perform form verbs, and to shut down forms.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="aa0ea-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="aa0ea-106">Header file:</span></span>  <br/> |<span data-ttu-id="aa0ea-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="aa0ea-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="aa0ea-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="aa0ea-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="aa0ea-109">表单对象</span><span class="sxs-lookup"><span data-stu-id="aa0ea-109">Form objects</span></span>  <br/> |
|<span data-ttu-id="aa0ea-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="aa0ea-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="aa0ea-111">表单服务器</span><span class="sxs-lookup"><span data-stu-id="aa0ea-111">Form servers</span></span>  <br/> |
|<span data-ttu-id="aa0ea-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="aa0ea-112">Called by:</span></span>  <br/> |<span data-ttu-id="aa0ea-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="aa0ea-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="aa0ea-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="aa0ea-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="aa0ea-115">IID_IMAPIForm</span><span class="sxs-lookup"><span data-stu-id="aa0ea-115">IID_IMAPIForm</span></span>  <br/> |
|<span data-ttu-id="aa0ea-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="aa0ea-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="aa0ea-117">LPMAPIFORM</span><span class="sxs-lookup"><span data-stu-id="aa0ea-117">LPMAPIFORM</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="aa0ea-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="aa0ea-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="aa0ea-119">SetViewContext</span><span class="sxs-lookup"><span data-stu-id="aa0ea-119">SetViewContext</span></span>](imapiform-setviewcontext.md) <br/> |<span data-ttu-id="aa0ea-120">建立表单的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="aa0ea-120">Establishes a view context for the form.</span></span>  <br/> |
|[<span data-ttu-id="aa0ea-121">GetViewContext</span><span class="sxs-lookup"><span data-stu-id="aa0ea-121">GetViewContext</span></span>](imapiform-getviewcontext.md) <br/> |<span data-ttu-id="aa0ea-122">返回窗体的当前视图上下文。</span><span class="sxs-lookup"><span data-stu-id="aa0ea-122">Returns the current view context for the form.</span></span>  <br/> |
|[<span data-ttu-id="aa0ea-123">ShutdownForm</span><span class="sxs-lookup"><span data-stu-id="aa0ea-123">ShutdownForm</span></span>](imapiform-shutdownform.md) <br/> |<span data-ttu-id="aa0ea-124">关闭表单。</span><span class="sxs-lookup"><span data-stu-id="aa0ea-124">Closes the form.</span></span>  <br/> |
|[<span data-ttu-id="aa0ea-125">DoVerb</span><span class="sxs-lookup"><span data-stu-id="aa0ea-125">DoVerb</span></span>](imapiform-doverb.md) <br/> |<span data-ttu-id="aa0ea-126">请求表单执行与特定动词关联的任何任务。</span><span class="sxs-lookup"><span data-stu-id="aa0ea-126">Requests that the form perform whatever tasks it associates with a specific verb.</span></span>  <br/> |
|[<span data-ttu-id="aa0ea-127">建议</span><span class="sxs-lookup"><span data-stu-id="aa0ea-127">Advise</span></span>](imapiform-advise.md) <br/> |<span data-ttu-id="aa0ea-128">注册窗体查看器，以接收有关影响窗体的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="aa0ea-128">Registers a form viewer for notifications about events that affect the form.</span></span>  <br/> |
|[<span data-ttu-id="aa0ea-129">非企业</span><span class="sxs-lookup"><span data-stu-id="aa0ea-129">Unadvise</span></span>](imapiform-unadvise.md) <br/> |<span data-ttu-id="aa0ea-130">通过调用 Advise 取消之前建立的表单查看器的通知 **注册**。</span><span class="sxs-lookup"><span data-stu-id="aa0ea-130">Cancels a registration for notifications with a form viewer previously established by calling **Advise**.</span></span>  <br/> |
|[<span data-ttu-id="aa0ea-131">GetLastError</span><span class="sxs-lookup"><span data-stu-id="aa0ea-131">GetLastError</span></span>](imapiform-getlasterror.md) <br/> |<span data-ttu-id="aa0ea-132">返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关表单对象发生的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="aa0ea-132">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the form object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="aa0ea-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa0ea-133">See also</span></span>



[<span data-ttu-id="aa0ea-134">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="aa0ea-134">MAPI Interfaces</span></span>](mapi-interfaces.md)

