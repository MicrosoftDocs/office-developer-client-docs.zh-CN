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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321775"
---
# <a name="imapiform--iunknown"></a><span data-ttu-id="c918e-103">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c918e-103">IMAPIForm : IUnknown</span></span>

  
  
<span data-ttu-id="c918e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c918e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c918e-105">使表单查看者能够使用表单视图上下文和表单通知, 执行表单谓词和关闭表单。</span><span class="sxs-lookup"><span data-stu-id="c918e-105">Enables form viewers to work with form view contexts and form notification, to perform form verbs, and to shut down forms.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c918e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c918e-106">Header file:</span></span>  <br/> |<span data-ttu-id="c918e-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="c918e-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="c918e-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="c918e-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="c918e-109">表单对象</span><span class="sxs-lookup"><span data-stu-id="c918e-109">Form objects</span></span>  <br/> |
|<span data-ttu-id="c918e-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="c918e-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="c918e-111">表单服务器</span><span class="sxs-lookup"><span data-stu-id="c918e-111">Form servers</span></span>  <br/> |
|<span data-ttu-id="c918e-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="c918e-112">Called by:</span></span>  <br/> |<span data-ttu-id="c918e-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="c918e-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="c918e-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="c918e-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="c918e-115">IID_IMAPIForm</span><span class="sxs-lookup"><span data-stu-id="c918e-115">IID_IMAPIForm</span></span>  <br/> |
|<span data-ttu-id="c918e-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="c918e-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="c918e-117">LPMAPIFORM</span><span class="sxs-lookup"><span data-stu-id="c918e-117">LPMAPIFORM</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="c918e-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="c918e-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="c918e-119">SetViewContext</span><span class="sxs-lookup"><span data-stu-id="c918e-119">SetViewContext</span></span>](imapiform-setviewcontext.md) <br/> |<span data-ttu-id="c918e-120">建立窗体的视图上下文。</span><span class="sxs-lookup"><span data-stu-id="c918e-120">Establishes a view context for the form.</span></span>  <br/> |
|[<span data-ttu-id="c918e-121">GetViewContext</span><span class="sxs-lookup"><span data-stu-id="c918e-121">GetViewContext</span></span>](imapiform-getviewcontext.md) <br/> |<span data-ttu-id="c918e-122">返回窗体的当前视图上下文。</span><span class="sxs-lookup"><span data-stu-id="c918e-122">Returns the current view context for the form.</span></span>  <br/> |
|[<span data-ttu-id="c918e-123">ShutdownForm</span><span class="sxs-lookup"><span data-stu-id="c918e-123">ShutdownForm</span></span>](imapiform-shutdownform.md) <br/> |<span data-ttu-id="c918e-124">关闭表单。</span><span class="sxs-lookup"><span data-stu-id="c918e-124">Closes the form.</span></span>  <br/> |
|[<span data-ttu-id="c918e-125">DoVerb</span><span class="sxs-lookup"><span data-stu-id="c918e-125">DoVerb</span></span>](imapiform-doverb.md) <br/> |<span data-ttu-id="c918e-126">请求表单执行与特定谓词相关联的任何任务。</span><span class="sxs-lookup"><span data-stu-id="c918e-126">Requests that the form perform whatever tasks it associates with a specific verb.</span></span>  <br/> |
|[<span data-ttu-id="c918e-127">她们</span><span class="sxs-lookup"><span data-stu-id="c918e-127">Advise</span></span>](imapiform-advise.md) <br/> |<span data-ttu-id="c918e-128">注册表单查看器, 以获取有关影响表单的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="c918e-128">Registers a form viewer for notifications about events that affect the form.</span></span>  <br/> |
|[<span data-ttu-id="c918e-129">Unadvise</span><span class="sxs-lookup"><span data-stu-id="c918e-129">Unadvise</span></span>](imapiform-unadvise.md) <br/> |<span data-ttu-id="c918e-130">取消之前通过调用**Advise**建立的表单查看器对通知的注册。</span><span class="sxs-lookup"><span data-stu-id="c918e-130">Cancels a registration for notifications with a form viewer previously established by calling **Advise**.</span></span>  <br/> |
|[<span data-ttu-id="c918e-131">GetLastError</span><span class="sxs-lookup"><span data-stu-id="c918e-131">GetLastError</span></span>](imapiform-getlasterror.md) <br/> |<span data-ttu-id="c918e-132">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个错误发生于表单对象的相关信息。</span><span class="sxs-lookup"><span data-stu-id="c918e-132">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the form object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c918e-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c918e-133">See also</span></span>



[<span data-ttu-id="c918e-134">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="c918e-134">MAPI Interfaces</span></span>](mapi-interfaces.md)

