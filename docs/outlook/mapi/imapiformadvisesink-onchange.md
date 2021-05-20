---
title: IMAPIFormAdviseSinkOnChange
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormAdviseSink.OnChange
api_type:
- COM
ms.assetid: d700b40f-e5b2-4d37-bf1f-8fd3dfa0dda5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 02663570e3173bbd696af732e71f060d9dee49bc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431895"
---
# <a name="imapiformadvisesinkonchange"></a><span data-ttu-id="fc60e-103">IMAPIFormAdviseSink::OnChange</span><span class="sxs-lookup"><span data-stu-id="fc60e-103">IMAPIFormAdviseSink::OnChange</span></span>

  
  
<span data-ttu-id="fc60e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fc60e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fc60e-105">指示表单查看器的状态发生了更改。</span><span class="sxs-lookup"><span data-stu-id="fc60e-105">Indicates that a change has occurred in the status of the form viewer.</span></span> 
  
```cpp
HRESULT OnChange(
  ULONG ulDir
);
```

## <a name="parameters"></a><span data-ttu-id="fc60e-106">参数</span><span class="sxs-lookup"><span data-stu-id="fc60e-106">Parameters</span></span>

 <span data-ttu-id="fc60e-107">_ulDir_</span><span class="sxs-lookup"><span data-stu-id="fc60e-107">_ulDir_</span></span>
  
> <span data-ttu-id="fc60e-108">[in]标志的位掩码，提供有关查看器中发生的更改和窗体中预期响应的信息。</span><span class="sxs-lookup"><span data-stu-id="fc60e-108">[in] A bitmask of flags that provides information about the change that has occurred in the viewer and the expected response in the form.</span></span> <span data-ttu-id="fc60e-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="fc60e-109">The following flags can be set:</span></span>
    
<span data-ttu-id="fc60e-110">VCSTATUS_CATEGORY</span><span class="sxs-lookup"><span data-stu-id="fc60e-110">VCSTATUS_CATEGORY</span></span> 
  
> <span data-ttu-id="fc60e-111">存在另一个类别中的下一封邮件或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="fc60e-111">There is a next or previous message in another category.</span></span> 
    
<span data-ttu-id="fc60e-112">VCSTATUS_INTERACTIVE</span><span class="sxs-lookup"><span data-stu-id="fc60e-112">VCSTATUS_INTERACTIVE</span></span> 
  
> <span data-ttu-id="fc60e-113">表单应显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="fc60e-113">The form should display a user interface.</span></span> <span data-ttu-id="fc60e-114">如果未设置此标志，则表单应禁止显示用户界面，即使该动作通常会导致显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="fc60e-114">If this flag is not set, the form should suppress displaying a user interface, even in response to a verb that usually causes a user interface to be displayed.</span></span> 
    
<span data-ttu-id="fc60e-115">VCSTATUS_MODAL</span><span class="sxs-lookup"><span data-stu-id="fc60e-115">VCSTATUS_MODAL</span></span> 
  
> <span data-ttu-id="fc60e-116">窗体对于窗体查看器是模式窗体。</span><span class="sxs-lookup"><span data-stu-id="fc60e-116">The form is to be modal to the form viewer.</span></span> 
    
<span data-ttu-id="fc60e-117">VCSTATUS_NEXT</span><span class="sxs-lookup"><span data-stu-id="fc60e-117">VCSTATUS_NEXT</span></span> 
  
> <span data-ttu-id="fc60e-118">表单查看器中还有下一条消息。</span><span class="sxs-lookup"><span data-stu-id="fc60e-118">There is a next message in the form viewer.</span></span> 
    
<span data-ttu-id="fc60e-119">VCSTATUS_PREV</span><span class="sxs-lookup"><span data-stu-id="fc60e-119">VCSTATUS_PREV</span></span> 
  
> <span data-ttu-id="fc60e-120">表单查看器中之前有一条消息。</span><span class="sxs-lookup"><span data-stu-id="fc60e-120">There is a previous message in the form viewer.</span></span> 
    
<span data-ttu-id="fc60e-121">VCSTATUS_READONLY</span><span class="sxs-lookup"><span data-stu-id="fc60e-121">VCSTATUS_READONLY</span></span> 
  
> <span data-ttu-id="fc60e-122">应禁用删除、提交和移动操作。</span><span class="sxs-lookup"><span data-stu-id="fc60e-122">Delete, submit, and move operations should be disabled.</span></span> 
    
<span data-ttu-id="fc60e-123">VCSTATUS_UNREAD</span><span class="sxs-lookup"><span data-stu-id="fc60e-123">VCSTATUS_UNREAD</span></span> 
  
> <span data-ttu-id="fc60e-124">窗体查看器中出现下一条或上一条未读邮件。</span><span class="sxs-lookup"><span data-stu-id="fc60e-124">There is a next or previous unread message in the form viewer.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fc60e-125">返回值</span><span class="sxs-lookup"><span data-stu-id="fc60e-125">Return value</span></span>

<span data-ttu-id="fc60e-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc60e-126">S_OK</span></span> 
  
> <span data-ttu-id="fc60e-127">通知成功。</span><span class="sxs-lookup"><span data-stu-id="fc60e-127">The notification was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fc60e-128">备注</span><span class="sxs-lookup"><span data-stu-id="fc60e-128">Remarks</span></span>

<span data-ttu-id="fc60e-129">表单查看器调用 **IMAPIFormAdviseSink：：OnChange** 方法来通知表单查看者状态的变化。</span><span class="sxs-lookup"><span data-stu-id="fc60e-129">Form viewers call the **IMAPIFormAdviseSink::OnChange** method to notify the form about a change in a viewer's status.</span></span> <span data-ttu-id="fc60e-130">通常，唯一的变化是基于查看器中是否存在下一封邮件或上VCSTATUS_NEXT或上一封邮件，设置或清除 VCSTATUS_NEXT 或 VCSTATUS_PREVIOUS 标志。</span><span class="sxs-lookup"><span data-stu-id="fc60e-130">Usually, the only change is setting or clearing the VCSTATUS_NEXT or VCSTATUS_PREVIOUS flag based on the presence or absence of a next or previous message in the viewer.</span></span> <span data-ttu-id="fc60e-131">然后，form 对象将启用或禁用它支持的任何下一个或上一个操作。</span><span class="sxs-lookup"><span data-stu-id="fc60e-131">Accordingly, the form object then enables or disables any next or previous actions it supports.</span></span> 
  
<span data-ttu-id="fc60e-132">创建视图VCSTATUS_MODAL VCSTATUS_INTERACTIVE在视图上下文中无法更改其设置。</span><span class="sxs-lookup"><span data-stu-id="fc60e-132">The settings of VCSTATUS_MODAL and VCSTATUS_INTERACTIVE cannot change in a view context after it has been created.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="fc60e-133">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="fc60e-133">Notes to implementers</span></span>

<span data-ttu-id="fc60e-134">此方法的特定实现完全依赖于表单的具体内容。</span><span class="sxs-lookup"><span data-stu-id="fc60e-134">The specific implementation of this method is completely dependent on the specifics of the form.</span></span> <span data-ttu-id="fc60e-135">大多数表单对象使用此方法来更改其用户界面 (例如，启用或禁用菜单命令或按钮以匹配查看器状态标志参数) 。</span><span class="sxs-lookup"><span data-stu-id="fc60e-135">Most form objects use this method to change their user interface (for example, to enable or disable menu commands or buttons to match the viewer status flags parameter).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc60e-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc60e-136">See also</span></span>



[<span data-ttu-id="fc60e-137">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="fc60e-137">IMAPIViewContext::ActivateNext</span></span>](imapiviewcontext-activatenext.md)
  
[<span data-ttu-id="fc60e-138">IMAPIFormAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fc60e-138">IMAPIFormAdviseSink : IUnknown</span></span>](imapiformadvisesinkiunknown.md)

