---
title: IMAPIFormAdviseSinkOnActivateNext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormAdviseSink.OnActivateNext
api_type:
- COM
ms.assetid: db621dfd-c6ad-42d2-8089-db40a63cab36
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7e8fb69e7d25420186d7269943c5d957311e813d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581753"
---
# <a name="imapiformadvisesinkonactivatenext"></a><span data-ttu-id="55c64-103">IMAPIFormAdviseSink::OnActivateNext</span><span class="sxs-lookup"><span data-stu-id="55c64-103">IMAPIFormAdviseSink::OnActivateNext</span></span>

  
  
<span data-ttu-id="55c64-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="55c64-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="55c64-105">指示表单是否可以处理的下一条消息以显示的邮件类。</span><span class="sxs-lookup"><span data-stu-id="55c64-105">Indicates whether the form can handle the message class of the next message to display.</span></span>
  
```cpp
HRESULT OnActivateNext(
  LPCSTR lpszMessageClass,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags,
  LPPERSISTMESSAGE FAR * ppPersistMessage
);
```

## <a name="parameters"></a><span data-ttu-id="55c64-106">参数</span><span class="sxs-lookup"><span data-stu-id="55c64-106">Parameters</span></span>

 <span data-ttu-id="55c64-107">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="55c64-107">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="55c64-108">[in]指向下一条消息的邮件类的指针。</span><span class="sxs-lookup"><span data-stu-id="55c64-108">[in] A pointer to the message class of the next message.</span></span>
    
 <span data-ttu-id="55c64-109">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="55c64-109">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="55c64-110">[in]客户端或提供程序定义的标志，复制**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性以显示，下一条消息中的位掩码，它提供邮件包含有关内容表的状态信息中。</span><span class="sxs-lookup"><span data-stu-id="55c64-110">[in] A bitmask of client-defined or provider-defined flags, copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of the next message to display, that provides status information regarding the contents table that the message is included in.</span></span>
    
 <span data-ttu-id="55c64-111">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="55c64-111">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="55c64-112">[in]指向标志复制**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性以显示的下一条消息中的位掩码的指示邮件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="55c64-112">[in] A pointer to a bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the next message to display that indicates the current state of the message.</span></span>
    
 <span data-ttu-id="55c64-113">_ppPersistMessage_</span><span class="sxs-lookup"><span data-stu-id="55c64-113">_ppPersistMessage_</span></span>
  
> <span data-ttu-id="55c64-114">[输出]指向用于新窗体，如果需要一个新窗体的窗体对象的[IPersistMessage](ipersistmessageiunknown.md)实现的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="55c64-114">[out] A pointer to a pointer to the [IPersistMessage](ipersistmessageiunknown.md) implementation for the form object used for the new form, if a new form is required.</span></span> <span data-ttu-id="55c64-115">如果当前窗体对象可用于显示和保存下一条消息，则可以返回为 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="55c64-115">A pointer to NULL can be returned if the current form object can be used to display and save the next message.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="55c64-116">返回值</span><span class="sxs-lookup"><span data-stu-id="55c64-116">Return value</span></span>

<span data-ttu-id="55c64-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="55c64-117">S_OK</span></span> 
  
> <span data-ttu-id="55c64-118">通知已成功和窗体可以处理下一条消息。</span><span class="sxs-lookup"><span data-stu-id="55c64-118">The notification was successful and the form can handle the next message.</span></span>
    
<span data-ttu-id="55c64-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="55c64-119">S_FALSE</span></span> 
  
> <span data-ttu-id="55c64-120">窗体并不处理的邮件类的下一条消息。</span><span class="sxs-lookup"><span data-stu-id="55c64-120">The form does not handle the message class of the next message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="55c64-121">注解</span><span class="sxs-lookup"><span data-stu-id="55c64-121">Remarks</span></span>

<span data-ttu-id="55c64-122">表单查看器调用**IMAPIFormAdviseSink::OnActivateNext**方法，可帮助确定是否可以在文件夹中显示下一条消息的窗体。</span><span class="sxs-lookup"><span data-stu-id="55c64-122">Form viewers call the **IMAPIFormAdviseSink::OnActivateNext** method to help the form determine whether it can display the next message in a folder.</span></span> <span data-ttu-id="55c64-123">下一条消息可能的任何类中，一条消息，但它通常是相同的类或相关的类。</span><span class="sxs-lookup"><span data-stu-id="55c64-123">The next message could be a message of any class, but typically it is of the same class or a related class.</span></span> <span data-ttu-id="55c64-124">这样使客户端应用程序能够重复使用表单对象尽可能读取效率同一个类的多个邮件的过程。</span><span class="sxs-lookup"><span data-stu-id="55c64-124">This makes the process of reading multiple messages of the same class more efficient by enabling client applications to reuse form objects whenever possible.</span></span> 
  
<span data-ttu-id="55c64-125">大多数窗体对象将使用_lpszMessageClass_参数指向的邮件类来确定是否能够处理下一条消息。</span><span class="sxs-lookup"><span data-stu-id="55c64-125">Most form objects will use the message class pointed to by the  _lpszMessageClass_ parameter to determine whether they can handle the next message.</span></span> <span data-ttu-id="55c64-126">通常窗体可以处理属于窗体的默认类的子类，除了所属的默认类的邮件类的消息。</span><span class="sxs-lookup"><span data-stu-id="55c64-126">Usually a form can handle messages that belong to classes of which the form's default class is a subclass, in addition to messages that belong to the default class.</span></span> <span data-ttu-id="55c64-127">但是，表单可以使用其他因素问题不确定是否可以处理消息，如下一条消息的发送或未发送的状态。</span><span class="sxs-lookup"><span data-stu-id="55c64-127">However, a form can use other factors to determine without question whether a message can be handled, such as the sent or unsent status of the next message.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="55c64-128">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="55c64-128">Notes to implementers</span></span>

<span data-ttu-id="55c64-129">如果窗体可以处理的邮件类中_ppPersistMessage_参数中返回 S_OK 和 NULL。</span><span class="sxs-lookup"><span data-stu-id="55c64-129">Return S_OK and NULL in the  _ppPersistMessage_ parameter if the form can handle the message class.</span></span> <span data-ttu-id="55c64-130">如果窗体可以创建新表单可以处理窗体处于无法处理的消息，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="55c64-130">If the form can create a new form that can handle the message that the form is unable to handle, follow these steps:</span></span> 
  
1. <span data-ttu-id="55c64-131">调用窗体的类工厂，以创建新的窗体对象的实例。</span><span class="sxs-lookup"><span data-stu-id="55c64-131">Call your form's class factory to create an instance of a new form object.</span></span>
    
2. <span data-ttu-id="55c64-132">在_ppPersistMessage_指针参数的内容中存储的实例。</span><span class="sxs-lookup"><span data-stu-id="55c64-132">Store that instance in the contents of the  _ppPersistMessage_ pointer parameter.</span></span> 
    
3. <span data-ttu-id="55c64-133">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="55c64-133">Return S_OK.</span></span>
    
<span data-ttu-id="55c64-134">表单查看器将使用指向_ppPersistMessage_对象所属的[IPersistMessage::Load](ipersistmessage-load.md)方法加载邮件。</span><span class="sxs-lookup"><span data-stu-id="55c64-134">The form viewer will load the message by using the [IPersistMessage::Load](ipersistmessage-load.md) method that belongs to the object pointed to by  _ppPersistMessage_.</span></span>
  
<span data-ttu-id="55c64-135">如果既没有表单，也可以创建窗体可以处理下一条消息，则返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="55c64-135">If neither the form nor a form that you can create can handle the next message, return S_FALSE.</span></span> <span data-ttu-id="55c64-136">但是，一般情况下，窗体不应该返回此值，因为它会导致降低表单查看器中的性能。</span><span class="sxs-lookup"><span data-stu-id="55c64-136">However, in general, forms should not return this value because it causes decreased performance in the form viewer.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="55c64-137">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="55c64-137">MFCMAPI reference</span></span>

<span data-ttu-id="55c64-138">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="55c64-138">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="55c64-139">**文件**</span><span class="sxs-lookup"><span data-stu-id="55c64-139">**File**</span></span>|<span data-ttu-id="55c64-140">**函数**</span><span class="sxs-lookup"><span data-stu-id="55c64-140">**Function**</span></span>|<span data-ttu-id="55c64-141">**Comment**</span><span class="sxs-lookup"><span data-stu-id="55c64-141">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="55c64-142">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="55c64-142">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="55c64-143">CMyMAPIFormViewer::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="55c64-143">CMyMAPIFormViewer::ActivateNext</span></span>  <br/> |<span data-ttu-id="55c64-144">MFCMAPI 使用**IMAPIFormAdviseSink::OnActivateNext**方法实现[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)方法。</span><span class="sxs-lookup"><span data-stu-id="55c64-144">MFCMAPI uses the **IMAPIFormAdviseSink::OnActivateNext** method to implement the [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md) method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="55c64-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55c64-145">See also</span></span>



[<span data-ttu-id="55c64-146">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="55c64-146">IMAPIViewContext::ActivateNext</span></span>](imapiviewcontext-activatenext.md)
  
[<span data-ttu-id="55c64-147">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="55c64-147">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
  
[<span data-ttu-id="55c64-148">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="55c64-148">IPersistMessage::Load</span></span>](ipersistmessage-load.md)
  
[<span data-ttu-id="55c64-149">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="55c64-149">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)
  
[<span data-ttu-id="55c64-150">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="55c64-150">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="55c64-151">IMAPIFormAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="55c64-151">IMAPIFormAdviseSink : IUnknown</span></span>](imapiformadvisesinkiunknown.md)


[<span data-ttu-id="55c64-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="55c64-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

