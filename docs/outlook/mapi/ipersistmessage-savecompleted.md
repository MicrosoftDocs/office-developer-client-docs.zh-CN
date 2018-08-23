---
title: IPersistMessageSaveCompleted
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.SaveCompleted
api_type:
- COM
ms.assetid: 83161011-90b4-49cb-9bcd-153a21a10977
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7813636abc1c4d6ad756c7cf670e21d4acb7f540
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592743"
---
# <a name="ipersistmessagesavecompleted"></a><span data-ttu-id="38bc8-103">IPersistMessage::SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="38bc8-103">IPersistMessage::SaveCompleted</span></span>

<span data-ttu-id="38bc8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38bc8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38bc8-105">通知窗体的保存操作已完成。</span><span class="sxs-lookup"><span data-stu-id="38bc8-105">Notifies the form that a save operation has been completed.</span></span> 
  
```cpp
HRESULT SaveCompleted(
  LPMESSAGE pMessage
);
```

## <a name="parameters"></a><span data-ttu-id="38bc8-106">参数</span><span class="sxs-lookup"><span data-stu-id="38bc8-106">Parameters</span></span>

<span data-ttu-id="38bc8-107">_pMessage_</span><span class="sxs-lookup"><span data-stu-id="38bc8-107">_pMessage_</span></span>
  
> <span data-ttu-id="38bc8-108">[in]一个指向新的已保存的邮件。</span><span class="sxs-lookup"><span data-stu-id="38bc8-108">[in] A pointer to the newly saved message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="38bc8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="38bc8-109">Return value</span></span>

<span data-ttu-id="38bc8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="38bc8-110">S_OK</span></span> 
  
> <span data-ttu-id="38bc8-111">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="38bc8-111">The notification was successful.</span></span>
    
<span data-ttu-id="38bc8-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="38bc8-112">E_INVALIDARG</span></span> 
  
> <span data-ttu-id="38bc8-113">_PMessage_参数为 NULL，表单中的[HandsOffFromNormal](handsofffromnormal-state.md)或[HandsOffAfterSave](handsoffaftersave-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="38bc8-113">The  _pMessage_ parameter is NULL and the form is either in the [HandsOffFromNormal](handsofffromnormal-state.md) or [HandsOffAfterSave](handsoffaftersave-state.md) state.</span></span> 
    
<span data-ttu-id="38bc8-114">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="38bc8-114">E_UNEXPECTED</span></span> 
  
> <span data-ttu-id="38bc8-115">窗体不处于以下状态之一：</span><span class="sxs-lookup"><span data-stu-id="38bc8-115">The form is not in one of the following states:</span></span>
    
   - <span data-ttu-id="38bc8-116">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="38bc8-116">HandsOffFromNormal</span></span>
    
   - <span data-ttu-id="38bc8-117">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="38bc8-117">HandsOffAfterSave</span></span>
    
   - [<span data-ttu-id="38bc8-118">NoScribble</span><span class="sxs-lookup"><span data-stu-id="38bc8-118">NoScribble</span></span>](noscribble-state.md)
    
## <a name="remarks"></a><span data-ttu-id="38bc8-119">注解</span><span class="sxs-lookup"><span data-stu-id="38bc8-119">Remarks</span></span>

<span data-ttu-id="38bc8-120">**IPersistMessage::SaveCompleted**调用表单查看器通知的表单的已保存所有挂起的更改。</span><span class="sxs-lookup"><span data-stu-id="38bc8-120">The **IPersistMessage::SaveCompleted** method is called by a form viewer to notify the form that all pending changes have been saved.</span></span> <span data-ttu-id="38bc8-121">仅当表单处于以下状态之一时，应该调用**SaveCompleted** :</span><span class="sxs-lookup"><span data-stu-id="38bc8-121">**SaveCompleted** should be called only when the form is in one of the following states:</span></span> 
  
- <span data-ttu-id="38bc8-122">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="38bc8-122">HandsOffFromNormal</span></span>
    
- <span data-ttu-id="38bc8-123">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="38bc8-123">HandsOffAfterSave</span></span>
    
- <span data-ttu-id="38bc8-124">NoScribble</span><span class="sxs-lookup"><span data-stu-id="38bc8-124">NoScribble</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="38bc8-125">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="38bc8-125">Notes to implementers</span></span>

<span data-ttu-id="38bc8-126">有多个可能的操作的**SaveCompleted**方法可执行，具体取决于哪些邮件指针参数包含，以及邮件是什么状态。</span><span class="sxs-lookup"><span data-stu-id="38bc8-126">There are several possible actions that the **SaveCompleted** method can perform, depending on what the message pointer parameter contains, and what state the message is in.</span></span> <span data-ttu-id="38bc8-127">但是，操作成功后，始终保存_pMessage_参数指向的消息和转换的当前状态表单到其[正常](normal-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="38bc8-127">However, when an action is successful, always save the current state of the message that the  _pMessage_ parameter points to and transition the form to its [Normal](normal-state.md) state.</span></span> 
  
<span data-ttu-id="38bc8-128">下表描述了影响的**SaveCompleted**实现中应采取的操作的条件。</span><span class="sxs-lookup"><span data-stu-id="38bc8-128">The following table describes the conditions that affect the actions you should take in your implementation of **SaveCompleted**.</span></span>
  
|<span data-ttu-id="38bc8-129">**条件**</span><span class="sxs-lookup"><span data-stu-id="38bc8-129">**Condition**</span></span>|<span data-ttu-id="38bc8-130">**操作**</span><span class="sxs-lookup"><span data-stu-id="38bc8-130">**Action**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38bc8-131">_PMessage_参数为 NULL，并且[IPersistMessage::Save](ipersistmessage-save.md)方法的_fSameAsLoad_参数设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="38bc8-131">The  _pMessage_ parameter is NULL and the  _fSameAsLoad_ parameter of the [IPersistMessage::Save](ipersistmessage-save.md) method is set to TRUE.</span></span>  <br/> |<span data-ttu-id="38bc8-132">呼叫所有已注册的查看器的[IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md)方法中，将表单作为干净，并返回 S_OK 标记。</span><span class="sxs-lookup"><span data-stu-id="38bc8-132">Call the [IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md) method of all registered viewers, mark the form as clean, and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="38bc8-133">_PMessage_参数为 NULL，并且**IPersistMessage::Save**方法的_fSameAsLoad_参数设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="38bc8-133">The  _pMessage_ parameter is NULL and the  _fSameAsLoad_ parameter of the **IPersistMessage::Save** method is set to FALSE.</span></span>  <br/> |<span data-ttu-id="38bc8-134">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="38bc8-134">Return S_OK.</span></span>  <br/> |
|<span data-ttu-id="38bc8-135">窗体处于 HandsOffFromNormal 状态。</span><span class="sxs-lookup"><span data-stu-id="38bc8-135">The form is in the HandsOffFromNormal state.</span></span>  <br/> |<span data-ttu-id="38bc8-136">将当前的邮件释放，并将它替换_pMessage_参数指向的消息。</span><span class="sxs-lookup"><span data-stu-id="38bc8-136">Release the current message and replace it with the message pointed to by the  _pMessage_ parameter.</span></span> <span data-ttu-id="38bc8-137">调用替换邮件[IUnknown::AddRef](http://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法，并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="38bc8-137">Call the replacement message's [IUnknown::AddRef](http://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) method and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="38bc8-138">窗体处于 HandsOffAfterSave 状态。</span><span class="sxs-lookup"><span data-stu-id="38bc8-138">The form is in the HandsOffAfterSave state.</span></span>  <br/> |<span data-ttu-id="38bc8-139">呼叫所有已注册的查看器的**IMAPIViewAdviseSink::OnSaved**方法中，将表单作为干净，并返回 S_OK 标记。</span><span class="sxs-lookup"><span data-stu-id="38bc8-139">Call the **IMAPIViewAdviseSink::OnSaved** method of all registered viewers, mark the form as clean, and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="38bc8-140">窗体处于[NoScribble](noscribble-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="38bc8-140">The form is in the [NoScribble](noscribble-state.md) state.</span></span>  <br/> |<span data-ttu-id="38bc8-141">将当前的邮件释放并将替换所指_pMessage_的邮件。</span><span class="sxs-lookup"><span data-stu-id="38bc8-141">Release the current message and replace it with the message pointed to by  _pMessage_.</span></span> <span data-ttu-id="38bc8-142">调用替换邮件**IUnknown::AddRef**方法。</span><span class="sxs-lookup"><span data-stu-id="38bc8-142">Call the replacement message's **IUnknown::AddRef** method.</span></span> <span data-ttu-id="38bc8-143">呼叫所有已注册的查看器的**IMAPIViewAdviseSink::OnSaved**方法中，将表单作为干净，并返回 S_OK 标记。</span><span class="sxs-lookup"><span data-stu-id="38bc8-143">Call the **IMAPIViewAdviseSink::OnSaved** method of all registered viewers, mark the form as clean, and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="38bc8-144">窗体处于 HandsOff 状态之一，并且_pMessage_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="38bc8-144">The form is in one of the HandsOff states and the  _pMessage_ parameter is set to NULL.</span></span>  <br/> |<span data-ttu-id="38bc8-145">返回 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="38bc8-145">Return E_INVALIDARG.</span></span>  <br/> |
|<span data-ttu-id="38bc8-146">窗体处于以外 HandsOff 状态的状态或 NoScribble 状态。</span><span class="sxs-lookup"><span data-stu-id="38bc8-146">The form is in a state other than one of the HandsOff states or the NoScribble state.</span></span>  <br/> |<span data-ttu-id="38bc8-147">返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="38bc8-147">Return E_UNEXPECTED.</span></span>  <br/> |
   
<span data-ttu-id="38bc8-148">有关保存存储对象的详细信息，请参阅[IPersistStorage::SaveCompleted](https://docs.microsoft.com/en-us/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted)或[IPersistFile::SaveCompleted](https://docs.microsoft.com/en-us/windows/desktop/api/objidl/nf-objidl-ipersistfile-savecompleted)方法的文档。</span><span class="sxs-lookup"><span data-stu-id="38bc8-148">For more information about saving storage objects, see the documentation for the [IPersistStorage::SaveCompleted](https://docs.microsoft.com/en-us/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted) or [IPersistFile::SaveCompleted](https://docs.microsoft.com/en-us/windows/desktop/api/objidl/nf-objidl-ipersistfile-savecompleted) methods.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="38bc8-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38bc8-149">See also</span></span>

- [<span data-ttu-id="38bc8-150">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="38bc8-150">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
- [<span data-ttu-id="38bc8-151">表单状态</span><span class="sxs-lookup"><span data-stu-id="38bc8-151">Form States</span></span>](form-states.md)
