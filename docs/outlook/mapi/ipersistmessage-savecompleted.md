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
# <a name="ipersistmessagesavecompleted"></a><span data-ttu-id="bc8a8-103">IPersistMessage::SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="bc8a8-103">IPersistMessage::SaveCompleted</span></span>

<span data-ttu-id="bc8a8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bc8a8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bc8a8-105">通知表单保存操作已完成。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-105">Notifies the form that a save operation has been completed.</span></span> 
  
```cpp
HRESULT SaveCompleted(
  LPMESSAGE pMessage
);
```

## <a name="parameters"></a><span data-ttu-id="bc8a8-106">参数</span><span class="sxs-lookup"><span data-stu-id="bc8a8-106">Parameters</span></span>

<span data-ttu-id="bc8a8-107">_pMessage_</span><span class="sxs-lookup"><span data-stu-id="bc8a8-107">_pMessage_</span></span>
  
> <span data-ttu-id="bc8a8-108">实时指向新保存的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-108">[in] A pointer to the newly saved message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bc8a8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bc8a8-109">Return value</span></span>

<span data-ttu-id="bc8a8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc8a8-110">S_OK</span></span> 
  
> <span data-ttu-id="bc8a8-111">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-111">The notification was successful.</span></span>
    
<span data-ttu-id="bc8a8-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bc8a8-112">E_INVALIDARG</span></span> 
  
> <span data-ttu-id="bc8a8-113">_pMessage_参数为 NULL, 该窗体处于[HandsOffFromNormal](handsofffromnormal-state.md)或[HandsOffAfterSave](handsoffaftersave-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-113">The  _pMessage_ parameter is NULL and the form is either in the [HandsOffFromNormal](handsofffromnormal-state.md) or [HandsOffAfterSave](handsoffaftersave-state.md) state.</span></span> 
    
<span data-ttu-id="bc8a8-114">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="bc8a8-114">E_UNEXPECTED</span></span> 
  
> <span data-ttu-id="bc8a8-115">表单不处于以下状态之一:</span><span class="sxs-lookup"><span data-stu-id="bc8a8-115">The form is not in one of the following states:</span></span>
    
   - <span data-ttu-id="bc8a8-116">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="bc8a8-116">HandsOffFromNormal</span></span>
    
   - <span data-ttu-id="bc8a8-117">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="bc8a8-117">HandsOffAfterSave</span></span>
    
   - [<span data-ttu-id="bc8a8-118">NoScribble</span><span class="sxs-lookup"><span data-stu-id="bc8a8-118">NoScribble</span></span>](noscribble-state.md)
    
## <a name="remarks"></a><span data-ttu-id="bc8a8-119">注解</span><span class="sxs-lookup"><span data-stu-id="bc8a8-119">Remarks</span></span>

<span data-ttu-id="bc8a8-120">表单查看器调用**IPersistMessage:: SaveCompleted**方法, 以通知表单已保存所有挂起的更改。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-120">The **IPersistMessage::SaveCompleted** method is called by a form viewer to notify the form that all pending changes have been saved.</span></span> <span data-ttu-id="bc8a8-121">仅当窗体处于以下状态之一时, 才应调用**SaveCompleted** :</span><span class="sxs-lookup"><span data-stu-id="bc8a8-121">**SaveCompleted** should be called only when the form is in one of the following states:</span></span> 
  
- <span data-ttu-id="bc8a8-122">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="bc8a8-122">HandsOffFromNormal</span></span>
    
- <span data-ttu-id="bc8a8-123">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="bc8a8-123">HandsOffAfterSave</span></span>
    
- <span data-ttu-id="bc8a8-124">NoScribble</span><span class="sxs-lookup"><span data-stu-id="bc8a8-124">NoScribble</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="bc8a8-125">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="bc8a8-125">Notes to implementers</span></span>

<span data-ttu-id="bc8a8-126">**SaveCompleted**方法可以执行几种可能的操作, 具体取决于邮件指针参数所包含的内容, 以及邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-126">There are several possible actions that the **SaveCompleted** method can perform, depending on what the message pointer parameter contains, and what state the message is in.</span></span> <span data-ttu-id="bc8a8-127">但是, 当操作成功时, 请始终保存_pMessage_参数指向的邮件的当前状态, 并将该表单转换为[正常](normal-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-127">However, when an action is successful, always save the current state of the message that the  _pMessage_ parameter points to and transition the form to its [Normal](normal-state.md) state.</span></span> 
  
<span data-ttu-id="bc8a8-128">下表介绍了影响您在**SaveCompleted**实现过程中应执行的操作的条件。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-128">The following table describes the conditions that affect the actions you should take in your implementation of **SaveCompleted**.</span></span>
  
|<span data-ttu-id="bc8a8-129">**条件**</span><span class="sxs-lookup"><span data-stu-id="bc8a8-129">**Condition**</span></span>|<span data-ttu-id="bc8a8-130">**操作**</span><span class="sxs-lookup"><span data-stu-id="bc8a8-130">**Action**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bc8a8-131">_pMessage_参数为 NULL, [IPersistMessage:: Save](ipersistmessage-save.md)方法的_fSameAsLoad_参数设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-131">The  _pMessage_ parameter is NULL and the  _fSameAsLoad_ parameter of the [IPersistMessage::Save](ipersistmessage-save.md) method is set to TRUE.</span></span>  <br/> |<span data-ttu-id="bc8a8-132">调用所有已注册查看器的[IMAPIViewAdviseSink:: OnSaved](imapiviewadvisesink-onsaved.md)方法, 将该窗体标记为干净, 并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-132">Call the [IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md) method of all registered viewers, mark the form as clean, and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="bc8a8-133">_pMessage_参数为 NULL, **IPersistMessage:: Save**方法的_fSameAsLoad_参数设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-133">The  _pMessage_ parameter is NULL and the  _fSameAsLoad_ parameter of the **IPersistMessage::Save** method is set to FALSE.</span></span>  <br/> |<span data-ttu-id="bc8a8-134">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-134">Return S_OK.</span></span>  <br/> |
|<span data-ttu-id="bc8a8-135">表单处于 "HandsOffFromNormal" 状态。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-135">The form is in the HandsOffFromNormal state.</span></span>  <br/> |<span data-ttu-id="bc8a8-136">释放当前邮件并将其替换为_pMessage_参数所指向的邮件。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-136">Release the current message and replace it with the message pointed to by the  _pMessage_ parameter.</span></span> <span data-ttu-id="bc8a8-137">调用替换邮件的[IUnknown:: AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-137">Call the replacement message's [IUnknown::AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) method and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="bc8a8-138">表单处于 "HandsOffAfterSave" 状态。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-138">The form is in the HandsOffAfterSave state.</span></span>  <br/> |<span data-ttu-id="bc8a8-139">调用所有已注册查看器的**IMAPIViewAdviseSink:: OnSaved**方法, 将该窗体标记为干净, 并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-139">Call the **IMAPIViewAdviseSink::OnSaved** method of all registered viewers, mark the form as clean, and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="bc8a8-140">表单处于 " [NoScribble](noscribble-state.md) " 状态。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-140">The form is in the [NoScribble](noscribble-state.md) state.</span></span>  <br/> |<span data-ttu-id="bc8a8-141">释放当前邮件并将其替换为_pMessage_指向的邮件。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-141">Release the current message and replace it with the message pointed to by  _pMessage_.</span></span> <span data-ttu-id="bc8a8-142">调用替换邮件的**IUnknown:: AddRef**方法。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-142">Call the replacement message's **IUnknown::AddRef** method.</span></span> <span data-ttu-id="bc8a8-143">调用所有已注册查看器的**IMAPIViewAdviseSink:: OnSaved**方法, 将该窗体标记为干净, 并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-143">Call the **IMAPIViewAdviseSink::OnSaved** method of all registered viewers, mark the form as clean, and return S_OK.</span></span>  <br/> |
|<span data-ttu-id="bc8a8-144">表单处于 HandsOff 状态之一, _pMessage_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-144">The form is in one of the HandsOff states and the  _pMessage_ parameter is set to NULL.</span></span>  <br/> |<span data-ttu-id="bc8a8-145">返回 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-145">Return E_INVALIDARG.</span></span>  <br/> |
|<span data-ttu-id="bc8a8-146">表单处于 HandsOff 状态或 NoScribble 状态之外的状态。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-146">The form is in a state other than one of the HandsOff states or the NoScribble state.</span></span>  <br/> |<span data-ttu-id="bc8a8-147">返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-147">Return E_UNEXPECTED.</span></span>  <br/> |
   
<span data-ttu-id="bc8a8-148">有关保存存储对象的详细信息, 请参阅[IPersistStorage:: SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted)或[IPersistFile:: SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersistfile-savecompleted)方法的相关文档。</span><span class="sxs-lookup"><span data-stu-id="bc8a8-148">For more information about saving storage objects, see the documentation for the [IPersistStorage::SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted) or [IPersistFile::SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersistfile-savecompleted) methods.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bc8a8-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc8a8-149">See also</span></span>

- [<span data-ttu-id="bc8a8-150">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bc8a8-150">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
- [<span data-ttu-id="bc8a8-151">表单状态</span><span class="sxs-lookup"><span data-stu-id="bc8a8-151">Form States</span></span>](form-states.md)
