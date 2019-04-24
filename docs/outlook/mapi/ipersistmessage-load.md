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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5024c2f8b88b54051e4b8400f4b3f14374b10c23
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317127"
---
# <a name="ipersistmessageload"></a><span data-ttu-id="74764-103">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="74764-103">IPersistMessage::Load</span></span>

  
  
<span data-ttu-id="74764-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="74764-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="74764-105">为指定的邮件加载窗体。</span><span class="sxs-lookup"><span data-stu-id="74764-105">Loads the form for a specified message.</span></span>
  
```cpp
HRESULT Load(
  LPMESSAGESITE pMessageSite,
  LPMESSAGE pMessage,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags
);
```

## <a name="parameters"></a><span data-ttu-id="74764-106">参数</span><span class="sxs-lookup"><span data-stu-id="74764-106">Parameters</span></span>

 <span data-ttu-id="74764-107">_pMessageSite_</span><span class="sxs-lookup"><span data-stu-id="74764-107">_pMessageSite_</span></span>
  
> <span data-ttu-id="74764-108">实时指向要加载的表单的邮件网站的指针。</span><span class="sxs-lookup"><span data-stu-id="74764-108">[in] A pointer to the message site for the form to be loaded.</span></span>
    
 <span data-ttu-id="74764-109">_pMessage_</span><span class="sxs-lookup"><span data-stu-id="74764-109">_pMessage_</span></span>
  
> <span data-ttu-id="74764-110">实时指向应为其加载表单的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="74764-110">[in] A pointer to the message for which the form should be loaded.</span></span>
    
 <span data-ttu-id="74764-111">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="74764-111">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="74764-112">实时客户端定义或提供程序定义的标志的位掩码, 从邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中进行复制, 这些标志提供有关邮件状态的信息。</span><span class="sxs-lookup"><span data-stu-id="74764-112">[in] A bitmask of client-defined or provider-defined flags, copied from the message's **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property, that provide information about the state of the message.</span></span>
    
 <span data-ttu-id="74764-113">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="74764-113">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="74764-114">实时从邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中复制的标志的位掩码, 可提供有关邮件状态的进一步信息。</span><span class="sxs-lookup"><span data-stu-id="74764-114">[in] A bitmask of flags, copied from the message's **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property, that provide further information about the state of the message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="74764-115">返回值</span><span class="sxs-lookup"><span data-stu-id="74764-115">Return value</span></span>

<span data-ttu-id="74764-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="74764-116">S_OK</span></span> 
  
> <span data-ttu-id="74764-117">表单已成功加载。</span><span class="sxs-lookup"><span data-stu-id="74764-117">The form was successfully loaded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="74764-118">注解</span><span class="sxs-lookup"><span data-stu-id="74764-118">Remarks</span></span>

<span data-ttu-id="74764-119">表单查看者调用**IPersistMessage:: load**方法以加载现有邮件的表单。</span><span class="sxs-lookup"><span data-stu-id="74764-119">Form viewers call the **IPersistMessage::Load** method to load a form for an existing message.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="74764-120">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="74764-120">Notes to implementers</span></span>

 <span data-ttu-id="74764-121">仅当窗体处于以下状态之一时, 才会调用**Load** :</span><span class="sxs-lookup"><span data-stu-id="74764-121">**Load** is called only when a form is in one of the following states:</span></span> 
  
- [<span data-ttu-id="74764-122">即</span><span class="sxs-lookup"><span data-stu-id="74764-122">Uninitialized</span></span>](uninitialized-state.md)
    
- [<span data-ttu-id="74764-123">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="74764-123">HandsOffAfterSave</span></span>](handsoffaftersave-state.md)
    
- [<span data-ttu-id="74764-124">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="74764-124">HandsOffFromNormal</span></span>](handsofffromnormal-state.md)
    
<span data-ttu-id="74764-125">如果表单查看器在窗体处于任何其他状态时调用**Load** , 则该方法返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="74764-125">If a form viewer calls **Load** while the form is in any other state, the method returns E_UNEXPECTED.</span></span> 
  
<span data-ttu-id="74764-126">如果您的表单具有对传递给**负载**的活动邮件网站的引用, 请释放原始网站, 因为它将不再使用。</span><span class="sxs-lookup"><span data-stu-id="74764-126">If your form has a reference to an active message site other than the one that is passed into **Load**, release the original site because it will no longer be used.</span></span> <span data-ttu-id="74764-127">将指针存储到邮件网站和来自_pMessageSite_和_pMessage_参数的消息, 并调用两个对象的[IUnknown:: AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法以增加其引用计数。</span><span class="sxs-lookup"><span data-stu-id="74764-127">Store the pointers to the message site and message from the  _pMessageSite_ and  _pMessage_ parameters and call both objects' [IUnknown::AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) methods to increment their reference counts.</span></span> 
  
<span data-ttu-id="74764-128">完成**AddRef**后, 将_ulMessageStatus_和_ulMessageFlags_参数中的属性存储到窗体中。</span><span class="sxs-lookup"><span data-stu-id="74764-128">After **AddRef** has completed, store the properties from the  _ulMessageStatus_ and  _ulMessageFlags_ parameters into the form.</span></span> <span data-ttu-id="74764-129">在显示窗体之前将其转换为[正常](normal-state.md)状态, 并通过调用其[IMAPIViewAdviseSink:: OnNewMessage](imapiviewadvisesink-onnewmessage.md)方法来通知注册的查看者。</span><span class="sxs-lookup"><span data-stu-id="74764-129">Transition the form to its [Normal](normal-state.md) state before displaying it, and notify registered viewers by calling their [IMAPIViewAdviseSink::OnNewMessage](imapiviewadvisesink-onnewmessage.md) methods.</span></span> 
  
<span data-ttu-id="74764-130">如果没有出现任何错误, 则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="74764-130">If no errors occur, return S_OK.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="74764-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74764-131">See also</span></span>



[<span data-ttu-id="74764-132">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="74764-132">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)
  
[<span data-ttu-id="74764-133">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="74764-133">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="74764-134">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="74764-134">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)


[<span data-ttu-id="74764-135">未初始化状态</span><span class="sxs-lookup"><span data-stu-id="74764-135">Uninitialized State</span></span>](uninitialized-state.md)
  
[<span data-ttu-id="74764-136">HandsOffAfterSave 状态</span><span class="sxs-lookup"><span data-stu-id="74764-136">HandsOffAfterSave State</span></span>](handsoffaftersave-state.md)
  
[<span data-ttu-id="74764-137">HandsOffFromNormal 状态</span><span class="sxs-lookup"><span data-stu-id="74764-137">HandsOffFromNormal State</span></span>](handsofffromnormal-state.md)
  
[<span data-ttu-id="74764-138">表单状态</span><span class="sxs-lookup"><span data-stu-id="74764-138">Form States</span></span>](form-states.md)


[<span data-ttu-id="74764-139">IPersistStorage:: Load</span><span class="sxs-lookup"><span data-stu-id="74764-139">IPersistStorage::Load</span></span>](https://msdn.microsoft.com/library/34379b8d-4e00-49cd-9fd1-65f88746c61a.aspx)
  
[<span data-ttu-id="74764-140">IPersistStream:: Load</span><span class="sxs-lookup"><span data-stu-id="74764-140">IPersistStream::Load</span></span>](https://msdn.microsoft.com/library/351e1187-9959-4542-8778-925457c3b8e3.aspx)
  
[<span data-ttu-id="74764-141">IPersistFile:: Load</span><span class="sxs-lookup"><span data-stu-id="74764-141">IPersistFile::Load</span></span>](https://msdn.microsoft.com/library/8391aa5c-fe6e-4b03-9eef-7958f75910a5.aspx)

