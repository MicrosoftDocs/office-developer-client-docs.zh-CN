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
ms.openlocfilehash: d647b41018afbade91dffb2818b48b0738148855
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411762"
---
# <a name="imapiformadvisesinkonactivatenext"></a><span data-ttu-id="34c99-103">IMAPIFormAdviseSink::OnActivateNext</span><span class="sxs-lookup"><span data-stu-id="34c99-103">IMAPIFormAdviseSink::OnActivateNext</span></span>

  
  
<span data-ttu-id="34c99-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="34c99-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="34c99-105">指示表单是否可以处理要显示的下一封邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="34c99-105">Indicates whether the form can handle the message class of the next message to display.</span></span>
  
```cpp
HRESULT OnActivateNext(
  LPCSTR lpszMessageClass,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags,
  LPPERSISTMESSAGE FAR * ppPersistMessage
);
```

## <a name="parameters"></a><span data-ttu-id="34c99-106">参数</span><span class="sxs-lookup"><span data-stu-id="34c99-106">Parameters</span></span>

 <span data-ttu-id="34c99-107">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="34c99-107">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="34c99-108">[in]指向下一封邮件的邮件类的指针。</span><span class="sxs-lookup"><span data-stu-id="34c99-108">[in] A pointer to the message class of the next message.</span></span>
    
 <span data-ttu-id="34c99-109">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="34c99-109">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="34c99-110">[in]客户端定义或提供程序定义标志的位掩码，从要显示的下一封邮件的 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制，提供有关包含邮件的内容表的状态信息。</span><span class="sxs-lookup"><span data-stu-id="34c99-110">[in] A bitmask of client-defined or provider-defined flags, copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of the next message to display, that provides status information regarding the contents table that the message is included in.</span></span>
    
 <span data-ttu-id="34c99-111">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="34c99-111">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="34c99-112">[in]指向从要显示的下一封邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志的位掩码的指针，指示邮件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="34c99-112">[in] A pointer to a bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the next message to display that indicates the current state of the message.</span></span>
    
 <span data-ttu-id="34c99-113">_ppPersistMessage_</span><span class="sxs-lookup"><span data-stu-id="34c99-113">_ppPersistMessage_</span></span>
  
> <span data-ttu-id="34c99-114">[out]指向用于新表单的表单对象的 [IPersistMessage](ipersistmessageiunknown.md) 实现（如果需要新表单）的指针。</span><span class="sxs-lookup"><span data-stu-id="34c99-114">[out] A pointer to a pointer to the [IPersistMessage](ipersistmessageiunknown.md) implementation for the form object used for the new form, if a new form is required.</span></span> <span data-ttu-id="34c99-115">如果当前表单对象可用于显示和保存下一条消息，则返回一个指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="34c99-115">A pointer to NULL can be returned if the current form object can be used to display and save the next message.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="34c99-116">返回值</span><span class="sxs-lookup"><span data-stu-id="34c99-116">Return value</span></span>

<span data-ttu-id="34c99-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="34c99-117">S_OK</span></span> 
  
> <span data-ttu-id="34c99-118">通知成功，表单可以处理下一封邮件。</span><span class="sxs-lookup"><span data-stu-id="34c99-118">The notification was successful and the form can handle the next message.</span></span>
    
<span data-ttu-id="34c99-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="34c99-119">S_FALSE</span></span> 
  
> <span data-ttu-id="34c99-120">窗体不处理下一封邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="34c99-120">The form does not handle the message class of the next message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="34c99-121">备注</span><span class="sxs-lookup"><span data-stu-id="34c99-121">Remarks</span></span>

<span data-ttu-id="34c99-122">表单查看器调用 **IMAPIFormAdviseSink：：OnActivateNext** 方法，以帮助表单确定是否可以在文件夹中显示下一封邮件。</span><span class="sxs-lookup"><span data-stu-id="34c99-122">Form viewers call the **IMAPIFormAdviseSink::OnActivateNext** method to help the form determine whether it can display the next message in a folder.</span></span> <span data-ttu-id="34c99-123">下一封邮件可能是任何类的邮件，但通常为同一个类或相关类。</span><span class="sxs-lookup"><span data-stu-id="34c99-123">The next message could be a message of any class, but typically it is of the same class or a related class.</span></span> <span data-ttu-id="34c99-124">这样，通过允许客户端应用程序尽可能重复使用表单对象，可以更高效地读取同一类的多个消息。</span><span class="sxs-lookup"><span data-stu-id="34c99-124">This makes the process of reading multiple messages of the same class more efficient by enabling client applications to reuse form objects whenever possible.</span></span> 
  
<span data-ttu-id="34c99-125">大多数表单对象将使用  _lpszMessageClass_ 参数指向的消息类来确定它们是否可以处理下一封邮件。</span><span class="sxs-lookup"><span data-stu-id="34c99-125">Most form objects will use the message class pointed to by the  _lpszMessageClass_ parameter to determine whether they can handle the next message.</span></span> <span data-ttu-id="34c99-126">通常，除了属于默认类的邮件之外，窗体还可以处理属于其默认类的类的邮件。</span><span class="sxs-lookup"><span data-stu-id="34c99-126">Usually a form can handle messages that belong to classes of which the form's default class is a subclass, in addition to messages that belong to the default class.</span></span> <span data-ttu-id="34c99-127">但是，表单可以使用其他因素来确定是否可以处理邮件，如下一封邮件的已发送状态或未发送状态。</span><span class="sxs-lookup"><span data-stu-id="34c99-127">However, a form can use other factors to determine without question whether a message can be handled, such as the sent or unsent status of the next message.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="34c99-128">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="34c99-128">Notes to implementers</span></span>

<span data-ttu-id="34c99-129">如果S_OK可以处理邮件类，则返回  _ppPersistMessage_ 参数中的值和 NULL。</span><span class="sxs-lookup"><span data-stu-id="34c99-129">Return S_OK and NULL in the  _ppPersistMessage_ parameter if the form can handle the message class.</span></span> <span data-ttu-id="34c99-130">如果表单可以创建一个新表单来处理无法处理的邮件，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="34c99-130">If the form can create a new form that can handle the message that the form is unable to handle, follow these steps:</span></span> 
  
1. <span data-ttu-id="34c99-131">调用窗体的类工厂以创建一个新的窗体对象的实例。</span><span class="sxs-lookup"><span data-stu-id="34c99-131">Call your form's class factory to create an instance of a new form object.</span></span>
    
2. <span data-ttu-id="34c99-132">将实例存储在  _ppPersistMessage_ 指针参数的内容中。</span><span class="sxs-lookup"><span data-stu-id="34c99-132">Store that instance in the contents of the  _ppPersistMessage_ pointer parameter.</span></span> 
    
3. <span data-ttu-id="34c99-133">返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="34c99-133">Return S_OK.</span></span>
    
<span data-ttu-id="34c99-134">表单查看器将通过使用 [IPersistMessage：：Load](ipersistmessage-load.md) 方法加载邮件，该方法属于  _ppPersistMessage_ 指向的对象。</span><span class="sxs-lookup"><span data-stu-id="34c99-134">The form viewer will load the message by using the [IPersistMessage::Load](ipersistmessage-load.md) method that belongs to the object pointed to by  _ppPersistMessage_.</span></span>
  
<span data-ttu-id="34c99-135">如果窗体和可以创建的窗体均不能处理下一封邮件，则返回S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="34c99-135">If neither the form nor a form that you can create can handle the next message, return S_FALSE.</span></span> <span data-ttu-id="34c99-136">但是，通常，表单不应返回此值，因为它会导致在表单查看器中性能降低。</span><span class="sxs-lookup"><span data-stu-id="34c99-136">However, in general, forms should not return this value because it causes decreased performance in the form viewer.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="34c99-137">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="34c99-137">MFCMAPI reference</span></span>

<span data-ttu-id="34c99-138">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="34c99-138">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="34c99-139">**文件**</span><span class="sxs-lookup"><span data-stu-id="34c99-139">**File**</span></span>|<span data-ttu-id="34c99-140">**函数**</span><span class="sxs-lookup"><span data-stu-id="34c99-140">**Function**</span></span>|<span data-ttu-id="34c99-141">**备注**</span><span class="sxs-lookup"><span data-stu-id="34c99-141">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34c99-142">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="34c99-142">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="34c99-143">CMyMAPIFormViewer：：ActivateNext</span><span class="sxs-lookup"><span data-stu-id="34c99-143">CMyMAPIFormViewer::ActivateNext</span></span>  <br/> |<span data-ttu-id="34c99-144">MFCMAPI 使用 **IMAPIFormAdviseSink：：OnActivateNext** 方法实现 [IMAPIViewContext：：ActivateNext](imapiviewcontext-activatenext.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="34c99-144">MFCMAPI uses the **IMAPIFormAdviseSink::OnActivateNext** method to implement the [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md) method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="34c99-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34c99-145">See also</span></span>



[<span data-ttu-id="34c99-146">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="34c99-146">IMAPIViewContext::ActivateNext</span></span>](imapiviewcontext-activatenext.md)
  
[<span data-ttu-id="34c99-147">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34c99-147">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
  
[<span data-ttu-id="34c99-148">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="34c99-148">IPersistMessage::Load</span></span>](ipersistmessage-load.md)
  
[<span data-ttu-id="34c99-149">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="34c99-149">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)
  
[<span data-ttu-id="34c99-150">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="34c99-150">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="34c99-151">IMAPIFormAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34c99-151">IMAPIFormAdviseSink : IUnknown</span></span>](imapiformadvisesinkiunknown.md)


[<span data-ttu-id="34c99-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="34c99-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

