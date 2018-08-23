---
title: IMAPIFormAdviseSink IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormAdviseSink
api_type:
- COM
ms.assetid: 180022af-4c1c-408c-a3fe-ed075cef79ab
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cee58299147c9f97ff61a3b8c460125349910637
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594458"
---
# <a name="imapiformadvisesink--iunknown"></a><span data-ttu-id="e71bb-103">IMAPIFormAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e71bb-103">IMAPIFormAdviseSink : IUnknown</span></span>

  
  
<span data-ttu-id="e71bb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e71bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e71bb-105">允许表单服务器表单查看器从接收通知。</span><span class="sxs-lookup"><span data-stu-id="e71bb-105">Enables form servers to receive notifications from form viewers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e71bb-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="e71bb-106">Header file:</span></span>  <br/> |<span data-ttu-id="e71bb-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="e71bb-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="e71bb-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="e71bb-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="e71bb-109">窗体告知接收器对象</span><span class="sxs-lookup"><span data-stu-id="e71bb-109">Form advise sink objects</span></span>  <br/> |
|<span data-ttu-id="e71bb-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="e71bb-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="e71bb-111">表单服务器</span><span class="sxs-lookup"><span data-stu-id="e71bb-111">Form servers</span></span>  <br/> |
|<span data-ttu-id="e71bb-112">调用：</span><span class="sxs-lookup"><span data-stu-id="e71bb-112">Called by:</span></span>  <br/> |<span data-ttu-id="e71bb-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="e71bb-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="e71bb-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="e71bb-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="e71bb-115">IID_IMAPIFormAdviseSink</span><span class="sxs-lookup"><span data-stu-id="e71bb-115">IID_IMAPIFormAdviseSink</span></span>  <br/> |
|<span data-ttu-id="e71bb-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="e71bb-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="e71bb-117">LPMAPIFORMADVISESINK</span><span class="sxs-lookup"><span data-stu-id="e71bb-117">LPMAPIFORMADVISESINK</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="e71bb-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="e71bb-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="e71bb-119">OnChange</span><span class="sxs-lookup"><span data-stu-id="e71bb-119">OnChange</span></span>](imapiformadvisesink-onchange.md) <br/> |<span data-ttu-id="e71bb-120">指示在表单查看器的状态发生更改。</span><span class="sxs-lookup"><span data-stu-id="e71bb-120">Indicates that a change has occurred in the status of the form viewer.</span></span>  <br/> |
|[<span data-ttu-id="e71bb-121">OnActivateNext</span><span class="sxs-lookup"><span data-stu-id="e71bb-121">OnActivateNext</span></span>](imapiformadvisesink-onactivatenext.md) <br/> |<span data-ttu-id="e71bb-122">指示表单是否可以处理的下一条消息以显示的邮件类。</span><span class="sxs-lookup"><span data-stu-id="e71bb-122">Indicates whether the form can handle the message class of the next message to display.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e71bb-123">注解</span><span class="sxs-lookup"><span data-stu-id="e71bb-123">Remarks</span></span>

<span data-ttu-id="e71bb-124">表单服务器表单使用建议接收器对象而不是其 form 对象并将其包含实现**IMAPIFormAdviseSink** 。</span><span class="sxs-lookup"><span data-stu-id="e71bb-124">Form servers use a form advise sink object to implement **IMAPIFormAdviseSink** instead of including it with their form object.</span></span> <span data-ttu-id="e71bb-125">因此，表单查看器应产生预期失败的调用窗体[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)方法来获取此接口的指针。</span><span class="sxs-lookup"><span data-stu-id="e71bb-125">Therefore, form viewers should expect a failed call to a form's [IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx) method to obtain a pointer to this interface.</span></span> 
  
<span data-ttu-id="e71bb-126">窗体服务器调用注册通知的查看者的[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e71bb-126">Form servers call a viewer's [IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md) method to register for notifications.</span></span> <span data-ttu-id="e71bb-127">包含用作参数对**IMAPIFormAdviseSink**实施的指针。</span><span class="sxs-lookup"><span data-stu-id="e71bb-127">A pointer to their **IMAPIFormAdviseSink** implementation is included as a parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e71bb-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e71bb-128">See also</span></span>



[<span data-ttu-id="e71bb-129">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="e71bb-129">MAPI Interfaces</span></span>](mapi-interfaces.md)

