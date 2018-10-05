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
ms.openlocfilehash: 68c2af0cd8d7ccddf6aa6017cfb830b196ac0771
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392058"
---
# <a name="imapiformadvisesink--iunknown"></a><span data-ttu-id="b13a6-103">IMAPIFormAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b13a6-103">IMAPIFormAdviseSink : IUnknown</span></span>

  
  
<span data-ttu-id="b13a6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b13a6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b13a6-105">允许表单服务器表单查看器从接收通知。</span><span class="sxs-lookup"><span data-stu-id="b13a6-105">Enables form servers to receive notifications from form viewers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b13a6-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b13a6-106">Header file:</span></span>  <br/> |<span data-ttu-id="b13a6-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="b13a6-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="b13a6-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="b13a6-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="b13a6-109">窗体告知接收器对象</span><span class="sxs-lookup"><span data-stu-id="b13a6-109">Form advise sink objects</span></span>  <br/> |
|<span data-ttu-id="b13a6-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="b13a6-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="b13a6-111">表单服务器</span><span class="sxs-lookup"><span data-stu-id="b13a6-111">Form servers</span></span>  <br/> |
|<span data-ttu-id="b13a6-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="b13a6-112">Called by:</span></span>  <br/> |<span data-ttu-id="b13a6-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="b13a6-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="b13a6-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="b13a6-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="b13a6-115">IID_IMAPIFormAdviseSink</span><span class="sxs-lookup"><span data-stu-id="b13a6-115">IID_IMAPIFormAdviseSink</span></span>  <br/> |
|<span data-ttu-id="b13a6-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="b13a6-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="b13a6-117">LPMAPIFORMADVISESINK</span><span class="sxs-lookup"><span data-stu-id="b13a6-117">LPMAPIFORMADVISESINK</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="b13a6-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="b13a6-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="b13a6-119">OnChange</span><span class="sxs-lookup"><span data-stu-id="b13a6-119">OnChange</span></span>](imapiformadvisesink-onchange.md) <br/> |<span data-ttu-id="b13a6-120">指示在表单查看器的状态发生更改。</span><span class="sxs-lookup"><span data-stu-id="b13a6-120">Indicates that a change has occurred in the status of the form viewer.</span></span>  <br/> |
|[<span data-ttu-id="b13a6-121">OnActivateNext</span><span class="sxs-lookup"><span data-stu-id="b13a6-121">OnActivateNext</span></span>](imapiformadvisesink-onactivatenext.md) <br/> |<span data-ttu-id="b13a6-122">指示表单是否可以处理的下一条消息以显示的邮件类。</span><span class="sxs-lookup"><span data-stu-id="b13a6-122">Indicates whether the form can handle the message class of the next message to display.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b13a6-123">说明</span><span class="sxs-lookup"><span data-stu-id="b13a6-123">Remarks</span></span>

<span data-ttu-id="b13a6-124">表单服务器表单使用建议接收器对象而不是其 form 对象并将其包含实现**IMAPIFormAdviseSink** 。</span><span class="sxs-lookup"><span data-stu-id="b13a6-124">Form servers use a form advise sink object to implement **IMAPIFormAdviseSink** instead of including it with their form object.</span></span> <span data-ttu-id="b13a6-125">因此，表单查看器应产生预期失败的调用窗体[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)方法来获取此接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b13a6-125">Therefore, form viewers should expect a failed call to a form's [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) method to obtain a pointer to this interface.</span></span> 
  
<span data-ttu-id="b13a6-126">窗体服务器调用注册通知的查看者的[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b13a6-126">Form servers call a viewer's [IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md) method to register for notifications.</span></span> <span data-ttu-id="b13a6-127">包含用作参数对**IMAPIFormAdviseSink**实施的指针。</span><span class="sxs-lookup"><span data-stu-id="b13a6-127">A pointer to their **IMAPIFormAdviseSink** implementation is included as a parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b13a6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b13a6-128">See also</span></span>



[<span data-ttu-id="b13a6-129">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="b13a6-129">MAPI Interfaces</span></span>](mapi-interfaces.md)

