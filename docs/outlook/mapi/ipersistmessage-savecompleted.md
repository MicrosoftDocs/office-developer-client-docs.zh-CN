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
ms.openlocfilehash: 021be209a2b2c891b668fa401500d6220619f9bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317134"
---
# <a name="ipersistmessagesavecompleted"></a><span data-ttu-id="4662f-103">IPersistMessage::SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="4662f-103">IPersistMessage::SaveCompleted</span></span>

<span data-ttu-id="4662f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4662f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4662f-105">通知窗体保存操作已完成。</span><span class="sxs-lookup"><span data-stu-id="4662f-105">Notifies the form that a save operation has been completed.</span></span> 
  
```cpp
HRESULT SaveCompleted(
  LPMESSAGE pMessage
);
```

## <a name="parameters"></a><span data-ttu-id="4662f-106">参数</span><span class="sxs-lookup"><span data-stu-id="4662f-106">Parameters</span></span>

<span data-ttu-id="4662f-107">_pMessage_</span><span class="sxs-lookup"><span data-stu-id="4662f-107">_pMessage_</span></span>
  
> <span data-ttu-id="4662f-108">[in]指向新保存的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="4662f-108">[in] A pointer to the newly saved message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4662f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4662f-109">Return value</span></span>

<span data-ttu-id="4662f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4662f-110">S_OK</span></span> 
  
> <span data-ttu-id="4662f-111">通知成功。</span><span class="sxs-lookup"><span data-stu-id="4662f-111">The notification was successful.</span></span>
    
<span data-ttu-id="4662f-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4662f-112">E_INVALIDARG</span></span> 
  
> <span data-ttu-id="4662f-113">_pMessage_ 参数为 NULL，并且表单为 [HandsOffFromNormal](handsofffromnormal-state.md)或 [HandsOffAfterSave](handsoffaftersave-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="4662f-113">The  _pMessage_ parameter is NULL and the form is either in the [HandsOffFromNormal](handsofffromnormal-state.md) or [HandsOffAfterSave](handsoffaftersave-state.md) state.</span></span> 
    
<span data-ttu-id="4662f-114">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="4662f-114">E_UNEXPECTED</span></span> 
  
> <span data-ttu-id="4662f-115">表单未在下列状态之一：</span><span class="sxs-lookup"><span data-stu-id="4662f-115">The form is not in one of the following states:</span></span>
    
   - <span data-ttu-id="4662f-116">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="4662f-116">HandsOffFromNormal</span></span>
    
   - <span data-ttu-id="4662f-117">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="4662f-117">HandsOffAfterSave</span></span>
    
   - [<span data-ttu-id="4662f-118">NoScribble</span><span class="sxs-lookup"><span data-stu-id="4662f-118">NoScribble</span></span>](noscribble-state.md)
    
## <a name="remarks"></a><span data-ttu-id="4662f-119">备注</span><span class="sxs-lookup"><span data-stu-id="4662f-119">Remarks</span></span>

<span data-ttu-id="4662f-120">表单 **查看器调用 IPersistMessage：：SaveCompleted** 方法，以通知表单已保存所有挂起的更改。</span><span class="sxs-lookup"><span data-stu-id="4662f-120">The **IPersistMessage::SaveCompleted** method is called by a form viewer to notify the form that all pending changes have been saved.</span></span> <span data-ttu-id="4662f-121">只有在表单具有以下状态之一时，才应调用 **SaveCompleted：**</span><span class="sxs-lookup"><span data-stu-id="4662f-121">**SaveCompleted** should be called only when the form is in one of the following states:</span></span> 
  
- <span data-ttu-id="4662f-122">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="4662f-122">HandsOffFromNormal</span></span>
    
- <span data-ttu-id="4662f-123">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="4662f-123">HandsOffAfterSave</span></span>
    
- <span data-ttu-id="4662f-124">NoScribble</span><span class="sxs-lookup"><span data-stu-id="4662f-124">NoScribble</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="4662f-125">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="4662f-125">Notes to implementers</span></span>

<span data-ttu-id="4662f-126">**SaveCompleted** 方法可以执行几种可能的操作，具体取决于邮件指针参数包含哪些内容以及邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="4662f-126">There are several possible actions that the **SaveCompleted** method can perform, depending on what the message pointer parameter contains, and what state the message is in.</span></span> <span data-ttu-id="4662f-127">但是，当操作成功时，始终保存  _pMessage_ 参数指向的消息的当前状态，并转换窗体到 [其 Normal](normal-state.md) 状态。</span><span class="sxs-lookup"><span data-stu-id="4662f-127">However, when an action is successful, always save the current state of the message that the  _pMessage_ parameter points to and transition the form to its [Normal](normal-state.md) state.</span></span> 
  
<span data-ttu-id="4662f-128">下表介绍了影响应在 SaveCompleted 的实现中采取的 **操作的条件**。</span><span class="sxs-lookup"><span data-stu-id="4662f-128">The following table describes the conditions that affect the actions you should take in your implementation of **SaveCompleted**.</span></span>
  
|<span data-ttu-id="4662f-129">**条件**</span><span class="sxs-lookup"><span data-stu-id="4662f-129">**Condition**</span></span>|<span data-ttu-id="4662f-130">**操作**</span><span class="sxs-lookup"><span data-stu-id="4662f-130">**Action**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4662f-131">_pMessage 参数_ 为 [NULL，IPersistMessage：：Save](ipersistmessage-save.md)方法的 _fSameAsLoad_ 参数设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="4662f-131">The  _pMessage_ parameter is NULL and the  _fSameAsLoad_ parameter of the [IPersistMessage::Save](ipersistmessage-save.md) method is set to TRUE.</span></span>  <br/> |<span data-ttu-id="4662f-132">调用 [所有注册查看器的 IMAPIViewAdviseSink：：OnSaved](imapiviewadvisesink-onsaved.md) 方法，将表单标记为干净，并返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="4662f-132">Call the [IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md) method of all registered viewers, mark the form as clean, and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="4662f-133">_pMessage 参数_ 为 **NULL，IPersistMessage：：Save** 方法的 _fSameAsLoad_ 参数设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="4662f-133">The  _pMessage_ parameter is NULL and the  _fSameAsLoad_ parameter of the **IPersistMessage::Save** method is set to FALSE.</span></span>  <br/> |<span data-ttu-id="4662f-134">返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="4662f-134">Return S_OK.</span></span>  <br/> |
|<span data-ttu-id="4662f-135">表单位于 HandsOffFromNormal 状态。</span><span class="sxs-lookup"><span data-stu-id="4662f-135">The form is in the HandsOffFromNormal state.</span></span>  <br/> |<span data-ttu-id="4662f-136">释放当前邮件并将其替换为  _pMessage_ 参数指向的消息。</span><span class="sxs-lookup"><span data-stu-id="4662f-136">Release the current message and replace it with the message pointed to by the  _pMessage_ parameter.</span></span> <span data-ttu-id="4662f-137">调用替换邮件的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) 方法并返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="4662f-137">Call the replacement message's [IUnknown::AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) method and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="4662f-138">表单位于 HandsOffAfterSave 状态。</span><span class="sxs-lookup"><span data-stu-id="4662f-138">The form is in the HandsOffAfterSave state.</span></span>  <br/> |<span data-ttu-id="4662f-139">调用 **所有注册查看器的 IMAPIViewAdviseSink：：OnSaved** 方法，将表单标记为干净，并返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="4662f-139">Call the **IMAPIViewAdviseSink::OnSaved** method of all registered viewers, mark the form as clean, and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="4662f-140">表单的状态为[NoScribble。](noscribble-state.md)</span><span class="sxs-lookup"><span data-stu-id="4662f-140">The form is in the [NoScribble](noscribble-state.md) state.</span></span>  <br/> |<span data-ttu-id="4662f-141">释放当前邮件并将其替换为  _pMessage_ 指向的消息。</span><span class="sxs-lookup"><span data-stu-id="4662f-141">Release the current message and replace it with the message pointed to by  _pMessage_.</span></span> <span data-ttu-id="4662f-142">调用替换邮件的 **IUnknown：：AddRef** 方法。</span><span class="sxs-lookup"><span data-stu-id="4662f-142">Call the replacement message's **IUnknown::AddRef** method.</span></span> <span data-ttu-id="4662f-143">调用 **所有注册查看器的 IMAPIViewAdviseSink：：OnSaved** 方法，将表单标记为干净，并返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="4662f-143">Call the **IMAPIViewAdviseSink::OnSaved** method of all registered viewers, mark the form as clean, and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="4662f-144">表单为 HandsOff 状态之一  _，pMessage_ 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4662f-144">The form is in one of the HandsOff states and the  _pMessage_ parameter is set to NULL.</span></span>  <br/> |<span data-ttu-id="4662f-145">返回E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="4662f-145">Return E_INVALIDARG.</span></span>  <br/> |
|<span data-ttu-id="4662f-146">表单的状态不是 HandsOff 状态或 NoScribble 状态之一。</span><span class="sxs-lookup"><span data-stu-id="4662f-146">The form is in a state other than one of the HandsOff states or the NoScribble state.</span></span>  <br/> |<span data-ttu-id="4662f-147">返回E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="4662f-147">Return E_UNEXPECTED.</span></span>  <br/> |
   
<span data-ttu-id="4662f-148">有关保存存储对象的信息，请参阅 [IPersistStorage：：SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted) 或 [IPersistFile：：SaveCompleted 方法](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersistfile-savecompleted) 的文档。</span><span class="sxs-lookup"><span data-stu-id="4662f-148">For more information about saving storage objects, see the documentation for the [IPersistStorage::SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted) or [IPersistFile::SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersistfile-savecompleted) methods.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4662f-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4662f-149">See also</span></span>

- [<span data-ttu-id="4662f-150">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4662f-150">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
- [<span data-ttu-id="4662f-151">表单状态</span><span class="sxs-lookup"><span data-stu-id="4662f-151">Form States</span></span>](form-states.md)
