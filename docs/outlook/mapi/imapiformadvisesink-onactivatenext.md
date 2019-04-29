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
# <a name="imapiformadvisesinkonactivatenext"></a><span data-ttu-id="9c00b-103">IMAPIFormAdviseSink::OnActivateNext</span><span class="sxs-lookup"><span data-stu-id="9c00b-103">IMAPIFormAdviseSink::OnActivateNext</span></span>

  
  
<span data-ttu-id="9c00b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c00b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9c00b-105">指示表单是否可以处理要显示的下一封邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="9c00b-105">Indicates whether the form can handle the message class of the next message to display.</span></span>
  
```cpp
HRESULT OnActivateNext(
  LPCSTR lpszMessageClass,
  ULONG ulMessageStatus,
  ULONG ulMessageFlags,
  LPPERSISTMESSAGE FAR * ppPersistMessage
);
```

## <a name="parameters"></a><span data-ttu-id="9c00b-106">参数</span><span class="sxs-lookup"><span data-stu-id="9c00b-106">Parameters</span></span>

 <span data-ttu-id="9c00b-107">_lpszMessageClass_</span><span class="sxs-lookup"><span data-stu-id="9c00b-107">_lpszMessageClass_</span></span>
  
> <span data-ttu-id="9c00b-108">实时指向下一封邮件的邮件类的指针。</span><span class="sxs-lookup"><span data-stu-id="9c00b-108">[in] A pointer to the message class of the next message.</span></span>
    
 <span data-ttu-id="9c00b-109">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="9c00b-109">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="9c00b-110">实时客户端定义或提供程序定义的标志的位掩码, 从下一条消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制到显示, 提供有关邮件包含的内容表的状态信息实时.</span><span class="sxs-lookup"><span data-stu-id="9c00b-110">[in] A bitmask of client-defined or provider-defined flags, copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of the next message to display, that provides status information regarding the contents table that the message is included in.</span></span>
    
 <span data-ttu-id="9c00b-111">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="9c00b-111">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="9c00b-112">实时一个指针, 指向从下一个要显示的消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中复制的标志位掩码, 该消息表示邮件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="9c00b-112">[in] A pointer to a bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of the next message to display that indicates the current state of the message.</span></span>
    
 <span data-ttu-id="9c00b-113">_ppPersistMessage_</span><span class="sxs-lookup"><span data-stu-id="9c00b-113">_ppPersistMessage_</span></span>
  
> <span data-ttu-id="9c00b-114">排除一个指针, 指向一个指向用于新表单的 form 对象的[IPersistMessage](ipersistmessageiunknown.md)实现的指针 (如果需要新表单)。</span><span class="sxs-lookup"><span data-stu-id="9c00b-114">[out] A pointer to a pointer to the [IPersistMessage](ipersistmessageiunknown.md) implementation for the form object used for the new form, if a new form is required.</span></span> <span data-ttu-id="9c00b-115">如果当前窗体对象可用于显示并保存下一封邮件, 则可以返回指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="9c00b-115">A pointer to NULL can be returned if the current form object can be used to display and save the next message.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="9c00b-116">返回值</span><span class="sxs-lookup"><span data-stu-id="9c00b-116">Return value</span></span>

<span data-ttu-id="9c00b-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c00b-117">S_OK</span></span> 
  
> <span data-ttu-id="9c00b-118">通知已成功, 表单可以处理下一封邮件。</span><span class="sxs-lookup"><span data-stu-id="9c00b-118">The notification was successful and the form can handle the next message.</span></span>
    
<span data-ttu-id="9c00b-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9c00b-119">S_FALSE</span></span> 
  
> <span data-ttu-id="9c00b-120">表单不处理下一封邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="9c00b-120">The form does not handle the message class of the next message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9c00b-121">说明</span><span class="sxs-lookup"><span data-stu-id="9c00b-121">Remarks</span></span>

<span data-ttu-id="9c00b-122">表单查看者调用**IMAPIFormAdviseSink:: OnActivateNext**方法, 以帮助表单确定是否可以在文件夹中显示下一封邮件。</span><span class="sxs-lookup"><span data-stu-id="9c00b-122">Form viewers call the **IMAPIFormAdviseSink::OnActivateNext** method to help the form determine whether it can display the next message in a folder.</span></span> <span data-ttu-id="9c00b-123">下一封邮件可能是任何类的消息, 但通常是同一个类或相关类。</span><span class="sxs-lookup"><span data-stu-id="9c00b-123">The next message could be a message of any class, but typically it is of the same class or a related class.</span></span> <span data-ttu-id="9c00b-124">这样, 客户端应用程序可以尽可能重用表单对象, 从而使读取相同类的多个邮件的过程更为有效。</span><span class="sxs-lookup"><span data-stu-id="9c00b-124">This makes the process of reading multiple messages of the same class more efficient by enabling client applications to reuse form objects whenever possible.</span></span> 
  
<span data-ttu-id="9c00b-125">大多数窗体对象将使用由_lpszMessageClass_参数指向的邮件类来确定它们是否可以处理下一封邮件。</span><span class="sxs-lookup"><span data-stu-id="9c00b-125">Most form objects will use the message class pointed to by the  _lpszMessageClass_ parameter to determine whether they can handle the next message.</span></span> <span data-ttu-id="9c00b-126">通常情况下, 窗体不仅可以处理属于窗体的默认类的类的邮件, 还可以处理属于默认类的邮件的子类。</span><span class="sxs-lookup"><span data-stu-id="9c00b-126">Usually a form can handle messages that belong to classes of which the form's default class is a subclass, in addition to messages that belong to the default class.</span></span> <span data-ttu-id="9c00b-127">但是, 窗体可以使用其他因素来确定是否可以处理邮件, 例如下一封邮件的已发送或未发送状态。</span><span class="sxs-lookup"><span data-stu-id="9c00b-127">However, a form can use other factors to determine without question whether a message can be handled, such as the sent or unsent status of the next message.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="9c00b-128">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="9c00b-128">Notes to implementers</span></span>

<span data-ttu-id="9c00b-129">如果窗体可以处理邮件类, 则在_ppPersistMessage_参数中返回 S_OK 和 NULL。</span><span class="sxs-lookup"><span data-stu-id="9c00b-129">Return S_OK and NULL in the  _ppPersistMessage_ parameter if the form can handle the message class.</span></span> <span data-ttu-id="9c00b-130">如果表单可以创建可处理表单无法处理的邮件的新表单, 请按照以下步骤操作:</span><span class="sxs-lookup"><span data-stu-id="9c00b-130">If the form can create a new form that can handle the message that the form is unable to handle, follow these steps:</span></span> 
  
1. <span data-ttu-id="9c00b-131">调用表单的类工厂以创建新表单对象的实例。</span><span class="sxs-lookup"><span data-stu-id="9c00b-131">Call your form's class factory to create an instance of a new form object.</span></span>
    
2. <span data-ttu-id="9c00b-132">将该实例存储在_ppPersistMessage_指针参数的内容中。</span><span class="sxs-lookup"><span data-stu-id="9c00b-132">Store that instance in the contents of the  _ppPersistMessage_ pointer parameter.</span></span> 
    
3. <span data-ttu-id="9c00b-133">返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="9c00b-133">Return S_OK.</span></span>
    
<span data-ttu-id="9c00b-134">表单查看器将使用[IPersistMessage:: load](ipersistmessage-load.md)方法加载邮件, 该对象属于_ppPersistMessage_指向的对象。</span><span class="sxs-lookup"><span data-stu-id="9c00b-134">The form viewer will load the message by using the [IPersistMessage::Load](ipersistmessage-load.md) method that belongs to the object pointed to by  _ppPersistMessage_.</span></span>
  
<span data-ttu-id="9c00b-135">如果既不能创建的窗体也不能处理下一封邮件, 则返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="9c00b-135">If neither the form nor a form that you can create can handle the next message, return S_FALSE.</span></span> <span data-ttu-id="9c00b-136">不过, 通常情况下, 窗体不应返回此值, 因为它会导致表单查看器中的性能下降。</span><span class="sxs-lookup"><span data-stu-id="9c00b-136">However, in general, forms should not return this value because it causes decreased performance in the form viewer.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9c00b-137">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="9c00b-137">MFCMAPI reference</span></span>

<span data-ttu-id="9c00b-138">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9c00b-138">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9c00b-139">**文件**</span><span class="sxs-lookup"><span data-stu-id="9c00b-139">**File**</span></span>|<span data-ttu-id="9c00b-140">**函数**</span><span class="sxs-lookup"><span data-stu-id="9c00b-140">**Function**</span></span>|<span data-ttu-id="9c00b-141">**备注**</span><span class="sxs-lookup"><span data-stu-id="9c00b-141">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c00b-142">MAPIFormFunctions</span><span class="sxs-lookup"><span data-stu-id="9c00b-142">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="9c00b-143">CMyMAPIFormViewer:: ActivateNext</span><span class="sxs-lookup"><span data-stu-id="9c00b-143">CMyMAPIFormViewer::ActivateNext</span></span>  <br/> |<span data-ttu-id="9c00b-144">MFCMAPI 使用**IMAPIFormAdviseSink:: OnActivateNext**方法实现[IMAPIViewContext:: ActivateNext](imapiviewcontext-activatenext.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9c00b-144">MFCMAPI uses the **IMAPIFormAdviseSink::OnActivateNext** method to implement the [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md) method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9c00b-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c00b-145">See also</span></span>



[<span data-ttu-id="9c00b-146">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="9c00b-146">IMAPIViewContext::ActivateNext</span></span>](imapiviewcontext-activatenext.md)
  
[<span data-ttu-id="9c00b-147">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9c00b-147">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)
  
[<span data-ttu-id="9c00b-148">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="9c00b-148">IPersistMessage::Load</span></span>](ipersistmessage-load.md)
  
[<span data-ttu-id="9c00b-149">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="9c00b-149">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)
  
[<span data-ttu-id="9c00b-150">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="9c00b-150">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="9c00b-151">IMAPIFormAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9c00b-151">IMAPIFormAdviseSink : IUnknown</span></span>](imapiformadvisesinkiunknown.md)


[<span data-ttu-id="9c00b-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9c00b-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

