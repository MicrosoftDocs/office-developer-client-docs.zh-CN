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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286602"
---
# <a name="imapiformadvisesink--iunknown"></a><span data-ttu-id="d9a91-103">IMAPIFormAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d9a91-103">IMAPIFormAdviseSink : IUnknown</span></span>

  
  
<span data-ttu-id="d9a91-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9a91-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9a91-105">使表单服务器能够接收来自表单查看器的通知。</span><span class="sxs-lookup"><span data-stu-id="d9a91-105">Enables form servers to receive notifications from form viewers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d9a91-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d9a91-106">Header file:</span></span>  <br/> |<span data-ttu-id="d9a91-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="d9a91-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="d9a91-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="d9a91-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="d9a91-109">表单建议接收对象</span><span class="sxs-lookup"><span data-stu-id="d9a91-109">Form advise sink objects</span></span>  <br/> |
|<span data-ttu-id="d9a91-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="d9a91-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="d9a91-111">表单服务器</span><span class="sxs-lookup"><span data-stu-id="d9a91-111">Form servers</span></span>  <br/> |
|<span data-ttu-id="d9a91-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="d9a91-112">Called by:</span></span>  <br/> |<span data-ttu-id="d9a91-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="d9a91-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="d9a91-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="d9a91-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="d9a91-115">IID_IMAPIFormAdviseSink</span><span class="sxs-lookup"><span data-stu-id="d9a91-115">IID_IMAPIFormAdviseSink</span></span>  <br/> |
|<span data-ttu-id="d9a91-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="d9a91-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="d9a91-117">LPMAPIFORMADVISESINK</span><span class="sxs-lookup"><span data-stu-id="d9a91-117">LPMAPIFORMADVISESINK</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="d9a91-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="d9a91-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="d9a91-119">OnChange</span><span class="sxs-lookup"><span data-stu-id="d9a91-119">OnChange</span></span>](imapiformadvisesink-onchange.md) <br/> |<span data-ttu-id="d9a91-120">指示表单查看器的状态发生了更改。</span><span class="sxs-lookup"><span data-stu-id="d9a91-120">Indicates that a change has occurred in the status of the form viewer.</span></span>  <br/> |
|[<span data-ttu-id="d9a91-121">OnActivateNext</span><span class="sxs-lookup"><span data-stu-id="d9a91-121">OnActivateNext</span></span>](imapiformadvisesink-onactivatenext.md) <br/> |<span data-ttu-id="d9a91-122">指示表单是否可以处理要显示的下一封邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="d9a91-122">Indicates whether the form can handle the message class of the next message to display.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d9a91-123">备注</span><span class="sxs-lookup"><span data-stu-id="d9a91-123">Remarks</span></span>

<span data-ttu-id="d9a91-124">表单服务器使用表单建议接收对象来实现 **IMAPIFormAdviseSink，而不是将 IMAPIFormAdviseSink** 与其 form 对象一起包含。</span><span class="sxs-lookup"><span data-stu-id="d9a91-124">Form servers use a form advise sink object to implement **IMAPIFormAdviseSink** instead of including it with their form object.</span></span> <span data-ttu-id="d9a91-125">因此，表单查看者应预期对表单 [的 IUnknown：：QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 方法的调用失败，以获取指向此接口的指针。</span><span class="sxs-lookup"><span data-stu-id="d9a91-125">Therefore, form viewers should expect a failed call to a form's [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) method to obtain a pointer to this interface.</span></span> 
  
<span data-ttu-id="d9a91-126">表单服务器调用查看器的 [IMAPIViewContext：：SetAdviseSink](imapiviewcontext-setadvisesink.md) 方法来注册通知。</span><span class="sxs-lookup"><span data-stu-id="d9a91-126">Form servers call a viewer's [IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md) method to register for notifications.</span></span> <span data-ttu-id="d9a91-127">指向 **IMAPIFormAdviseSink** 实现指针作为参数包含在内。</span><span class="sxs-lookup"><span data-stu-id="d9a91-127">A pointer to their **IMAPIFormAdviseSink** implementation is included as a parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d9a91-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9a91-128">See also</span></span>



[<span data-ttu-id="d9a91-129">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="d9a91-129">MAPI Interfaces</span></span>](mapi-interfaces.md)

