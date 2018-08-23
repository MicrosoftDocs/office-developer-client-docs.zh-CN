---
title: IPersistMessageLoad
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.Load
api_type:
- COM
ms.assetid: bd4646d2-8229-499d-91aa-3cbec72b9445
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6c7942d16cabc61eab55ab145b9c26a1799bbcc4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565170"
---
# <a name="ipersistmessageload"></a><span data-ttu-id="390bf-103">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="390bf-103">IPersistMessage::Load</span></span>

  
  
<span data-ttu-id="390bf-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="390bf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="390bf-105">加载指定的消息的窗体。</span><span class="sxs-lookup"><span data-stu-id="390bf-105">Loads the form for a specified message.</span></span>
  
```cpp
HRESULT Load(
  LPMESSAGESITE pMessageSite,
  LPMESSAGE pMessage,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags
);
```

## <a name="parameters"></a><span data-ttu-id="390bf-106">参数</span><span class="sxs-lookup"><span data-stu-id="390bf-106">Parameters</span></span>

 <span data-ttu-id="390bf-107">_pMessageSite_</span><span class="sxs-lookup"><span data-stu-id="390bf-107">_pMessageSite_</span></span>
  
> <span data-ttu-id="390bf-108">[in]指向要加载窗体的邮件网站的指针。</span><span class="sxs-lookup"><span data-stu-id="390bf-108">[in] A pointer to the message site for the form to be loaded.</span></span>
    
 <span data-ttu-id="390bf-109">_pMessage_</span><span class="sxs-lookup"><span data-stu-id="390bf-109">_pMessage_</span></span>
  
> <span data-ttu-id="390bf-110">[in]一个指向应为其加载窗体的邮件。</span><span class="sxs-lookup"><span data-stu-id="390bf-110">[in] A pointer to the message for which the form should be loaded.</span></span>
    
 <span data-ttu-id="390bf-111">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="390bf-111">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="390bf-112">[in]客户端或提供程序定义的标志，复制邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中的位掩码，提供有关邮件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="390bf-112">[in] A bitmask of client-defined or provider-defined flags, copied from the message's **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property, that provide information about the state of the message.</span></span>
    
 <span data-ttu-id="390bf-113">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="390bf-113">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="390bf-114">[in]标志，复制邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的位掩码的进一步提供有关邮件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="390bf-114">[in] A bitmask of flags, copied from the message's **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property, that provide further information about the state of the message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="390bf-115">返回值</span><span class="sxs-lookup"><span data-stu-id="390bf-115">Return value</span></span>

<span data-ttu-id="390bf-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="390bf-116">S_OK</span></span> 
  
> <span data-ttu-id="390bf-117">已成功加载窗体。</span><span class="sxs-lookup"><span data-stu-id="390bf-117">The form was successfully loaded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="390bf-118">注解</span><span class="sxs-lookup"><span data-stu-id="390bf-118">Remarks</span></span>

<span data-ttu-id="390bf-119">表单查看器调用**IPersistMessage::Load**方法以加载的现有邮件窗体。</span><span class="sxs-lookup"><span data-stu-id="390bf-119">Form viewers call the **IPersistMessage::Load** method to load a form for an existing message.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="390bf-120">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="390bf-120">Notes to implementers</span></span>

 <span data-ttu-id="390bf-121">仅当表单处于以下状态之一时调用**负载**：</span><span class="sxs-lookup"><span data-stu-id="390bf-121">**Load** is called only when a form is in one of the following states:</span></span> 
  
- [<span data-ttu-id="390bf-122">未初始化</span><span class="sxs-lookup"><span data-stu-id="390bf-122">Uninitialized</span></span>](uninitialized-state.md)
    
- [<span data-ttu-id="390bf-123">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="390bf-123">HandsOffAfterSave</span></span>](handsoffaftersave-state.md)
    
- [<span data-ttu-id="390bf-124">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="390bf-124">HandsOffFromNormal</span></span>](handsofffromnormal-state.md)
    
<span data-ttu-id="390bf-125">如果表单查看器调用**负载**在窗体中任何其他状态时，该方法将返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="390bf-125">If a form viewer calls **Load** while the form is in any other state, the method returns E_UNEXPECTED.</span></span> 
  
<span data-ttu-id="390bf-126">如果窗体有一个引用传递到**负载**以外的活动邮件网站，释放原始网站，因为不再使用它。</span><span class="sxs-lookup"><span data-stu-id="390bf-126">If your form has a reference to an active message site other than the one that is passed into **Load**, release the original site because it will no longer be used.</span></span> <span data-ttu-id="390bf-127">存储从_pMessageSite_和_pMessage_参数的消息网站和消息的指针和调用这两个对象的[IUnknown::AddRef](http://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法，以增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="390bf-127">Store the pointers to the message site and message from the  _pMessageSite_ and  _pMessage_ parameters and call both objects' [IUnknown::AddRef](http://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) methods to increment their reference counts.</span></span> 
  
<span data-ttu-id="390bf-128">**AddRef**完成后，存储到表单的_ulMessageStatus_和_ulMessageFlags_参数中的属性。</span><span class="sxs-lookup"><span data-stu-id="390bf-128">After **AddRef** has completed, store the properties from the  _ulMessageStatus_ and  _ulMessageFlags_ parameters into the form.</span></span> <span data-ttu-id="390bf-129">显示之前, 转换为其[普通](normal-state.md)状态窗体，并通过调用其[IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法通知注册的查看器。</span><span class="sxs-lookup"><span data-stu-id="390bf-129">Transition the form to its [Normal](normal-state.md) state before displaying it, and notify registered viewers by calling their [IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md) methods.</span></span> 
  
<span data-ttu-id="390bf-130">如果没有错误，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="390bf-130">If no errors occur, return S_OK.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="390bf-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="390bf-131">See also</span></span>



[<span data-ttu-id="390bf-132">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="390bf-132">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)
  
[<span data-ttu-id="390bf-133">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="390bf-133">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="390bf-134">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="390bf-134">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)


[<span data-ttu-id="390bf-135">Uninitialized 状态</span><span class="sxs-lookup"><span data-stu-id="390bf-135">Uninitialized State</span></span>](uninitialized-state.md)
  
[<span data-ttu-id="390bf-136">HandsOffAfterSave 状态</span><span class="sxs-lookup"><span data-stu-id="390bf-136">HandsOffAfterSave State</span></span>](handsoffaftersave-state.md)
  
[<span data-ttu-id="390bf-137">HandsOffFromNormal 状态</span><span class="sxs-lookup"><span data-stu-id="390bf-137">HandsOffFromNormal State</span></span>](handsofffromnormal-state.md)
  
[<span data-ttu-id="390bf-138">表单状态</span><span class="sxs-lookup"><span data-stu-id="390bf-138">Form States</span></span>](form-states.md)


[<span data-ttu-id="390bf-139">IPersistStorage::Load</span><span class="sxs-lookup"><span data-stu-id="390bf-139">IPersistStorage::Load</span></span>](http://msdn.microsoft.com/library/34379b8d-4e00-49cd-9fd1-65f88746c61a.aspx)
  
[<span data-ttu-id="390bf-140">IPersistStream::Load</span><span class="sxs-lookup"><span data-stu-id="390bf-140">IPersistStream::Load</span></span>](http://msdn.microsoft.com/library/351e1187-9959-4542-8778-925457c3b8e3.aspx)
  
[<span data-ttu-id="390bf-141">IPersistFile::Load</span><span class="sxs-lookup"><span data-stu-id="390bf-141">IPersistFile::Load</span></span>](http://msdn.microsoft.com/library/8391aa5c-fe6e-4b03-9eef-7958f75910a5.aspx)

