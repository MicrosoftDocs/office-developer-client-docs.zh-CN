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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e32157f41632b782fbacf87e0411c18d167b4279
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576678"
---
# <a name="imapiformadvisesinkonchange"></a><span data-ttu-id="f605b-103">IMAPIFormAdviseSink::OnChange</span><span class="sxs-lookup"><span data-stu-id="f605b-103">IMAPIFormAdviseSink::OnChange</span></span>

  
  
<span data-ttu-id="f605b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f605b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f605b-105">指示在表单查看器的状态发生更改。</span><span class="sxs-lookup"><span data-stu-id="f605b-105">Indicates that a change has occurred in the status of the form viewer.</span></span> 
  
```cpp
HRESULT OnChange(
  ULONG ulDir
);
```

## <a name="parameters"></a><span data-ttu-id="f605b-106">参数</span><span class="sxs-lookup"><span data-stu-id="f605b-106">Parameters</span></span>

 <span data-ttu-id="f605b-107">_ulDir_</span><span class="sxs-lookup"><span data-stu-id="f605b-107">_ulDir_</span></span>
  
> <span data-ttu-id="f605b-108">[in]位掩码的标志，提供有关在查看器和窗体中的预期的响应中未发生更改的信息。</span><span class="sxs-lookup"><span data-stu-id="f605b-108">[in] A bitmask of flags that provides information about the change that has occurred in the viewer and the expected response in the form.</span></span> <span data-ttu-id="f605b-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="f605b-109">The following flags can be set:</span></span>
    
<span data-ttu-id="f605b-110">VCSTATUS_CATEGORY</span><span class="sxs-lookup"><span data-stu-id="f605b-110">VCSTATUS_CATEGORY</span></span> 
  
> <span data-ttu-id="f605b-111">在其他类别没有下一个或上一条消息。</span><span class="sxs-lookup"><span data-stu-id="f605b-111">There is a next or previous message in another category.</span></span> 
    
<span data-ttu-id="f605b-112">VCSTATUS_INTERACTIVE</span><span class="sxs-lookup"><span data-stu-id="f605b-112">VCSTATUS_INTERACTIVE</span></span> 
  
> <span data-ttu-id="f605b-113">表单应显示的用户界面。</span><span class="sxs-lookup"><span data-stu-id="f605b-113">The form should display a user interface.</span></span> <span data-ttu-id="f605b-114">如果未设置此标志，表单应禁止显示用户界面，即使在响应通常会导致用户界面将显示动词。</span><span class="sxs-lookup"><span data-stu-id="f605b-114">If this flag is not set, the form should suppress displaying a user interface, even in response to a verb that usually causes a user interface to be displayed.</span></span> 
    
<span data-ttu-id="f605b-115">VCSTATUS_MODAL</span><span class="sxs-lookup"><span data-stu-id="f605b-115">VCSTATUS_MODAL</span></span> 
  
> <span data-ttu-id="f605b-116">窗体是模式窗体查看器。</span><span class="sxs-lookup"><span data-stu-id="f605b-116">The form is to be modal to the form viewer.</span></span> 
    
<span data-ttu-id="f605b-117">VCSTATUS_NEXT</span><span class="sxs-lookup"><span data-stu-id="f605b-117">VCSTATUS_NEXT</span></span> 
  
> <span data-ttu-id="f605b-118">在窗体查看器没有下一条消息。</span><span class="sxs-lookup"><span data-stu-id="f605b-118">There is a next message in the form viewer.</span></span> 
    
<span data-ttu-id="f605b-119">VCSTATUS_PREV</span><span class="sxs-lookup"><span data-stu-id="f605b-119">VCSTATUS_PREV</span></span> 
  
> <span data-ttu-id="f605b-120">在窗体查看器没有上一条消息。</span><span class="sxs-lookup"><span data-stu-id="f605b-120">There is a previous message in the form viewer.</span></span> 
    
<span data-ttu-id="f605b-121">VCSTATUS_READONLY</span><span class="sxs-lookup"><span data-stu-id="f605b-121">VCSTATUS_READONLY</span></span> 
  
> <span data-ttu-id="f605b-122">删除、 提交，和移动操作应被禁用。</span><span class="sxs-lookup"><span data-stu-id="f605b-122">Delete, submit, and move operations should be disabled.</span></span> 
    
<span data-ttu-id="f605b-123">VCSTATUS_UNREAD</span><span class="sxs-lookup"><span data-stu-id="f605b-123">VCSTATUS_UNREAD</span></span> 
  
> <span data-ttu-id="f605b-124">在窗体查看器没有下一页或上一页未读的邮件。</span><span class="sxs-lookup"><span data-stu-id="f605b-124">There is a next or previous unread message in the form viewer.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f605b-125">返回值</span><span class="sxs-lookup"><span data-stu-id="f605b-125">Return value</span></span>

<span data-ttu-id="f605b-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="f605b-126">S_OK</span></span> 
  
> <span data-ttu-id="f605b-127">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="f605b-127">The notification was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f605b-128">注解</span><span class="sxs-lookup"><span data-stu-id="f605b-128">Remarks</span></span>

<span data-ttu-id="f605b-129">表单查看器调用**IMAPIFormAdviseSink::OnChange**方法以通知有关查看器的状态更改窗体。</span><span class="sxs-lookup"><span data-stu-id="f605b-129">Form viewers call the **IMAPIFormAdviseSink::OnChange** method to notify the form about a change in a viewer's status.</span></span> <span data-ttu-id="f605b-130">通常，更改只是设置或清除基于存在查看器中的下一页或上一页邮件 VCSTATUS_NEXT 或 VCSTATUS_PREVIOUS 标志。</span><span class="sxs-lookup"><span data-stu-id="f605b-130">Usually, the only change is setting or clearing the VCSTATUS_NEXT or VCSTATUS_PREVIOUS flag based on the presence or absence of a next or previous message in the viewer.</span></span> <span data-ttu-id="f605b-131">因此，form 对象然后启用或禁用它支持的任何下一个或上一操作。</span><span class="sxs-lookup"><span data-stu-id="f605b-131">Accordingly, the form object then enables or disables any next or previous actions it supports.</span></span> 
  
<span data-ttu-id="f605b-132">创建它之后，VCSTATUS_MODAL 和 VCSTATUS_INTERACTIVE 的设置不能更改了视图上下文中。</span><span class="sxs-lookup"><span data-stu-id="f605b-132">The settings of VCSTATUS_MODAL and VCSTATUS_INTERACTIVE cannot change in a view context after it has been created.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="f605b-133">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="f605b-133">Notes to implementers</span></span>

<span data-ttu-id="f605b-134">具体的实现此方法是完全取决于该窗体的具体信息。</span><span class="sxs-lookup"><span data-stu-id="f605b-134">The specific implementation of this method is completely dependent on the specifics of the form.</span></span> <span data-ttu-id="f605b-135">大多数窗体对象使用此方法来更改其用户界面 （例如，若要启用或禁用菜单命令或按钮来查看器的状态标志参数匹配）。</span><span class="sxs-lookup"><span data-stu-id="f605b-135">Most form objects use this method to change their user interface (for example, to enable or disable menu commands or buttons to match the viewer status flags parameter).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f605b-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f605b-136">See also</span></span>



[<span data-ttu-id="f605b-137">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="f605b-137">IMAPIViewContext::ActivateNext</span></span>](imapiviewcontext-activatenext.md)
  
[<span data-ttu-id="f605b-138">IMAPIFormAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f605b-138">IMAPIFormAdviseSink : IUnknown</span></span>](imapiformadvisesinkiunknown.md)

