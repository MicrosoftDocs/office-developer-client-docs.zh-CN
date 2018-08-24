---
title: IMAPISupportReadReceipt
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ReadReceipt
api_type:
- COM
ms.assetid: ef31b61a-93b6-4ae8-bc71-f5ef5caf43f4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e785d42639d51dab154a0bde239f858a92ddd143
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588620"
---
# <a name="imapisupportreadreceipt"></a><span data-ttu-id="c8415-103">IMAPISupport::ReadReceipt</span><span class="sxs-lookup"><span data-stu-id="c8415-103">IMAPISupport::ReadReceipt</span></span>

  
  
<span data-ttu-id="c8415-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c8415-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c8415-105">生成一个读取或 nonread 的报销单以供一条消息。</span><span class="sxs-lookup"><span data-stu-id="c8415-105">Generates a read or nonread report for a message.</span></span>
  
```cpp
HRESULT ReadReceipt(
ULONG ulFlags,
LPMESSAGE lpReadMessage,
LPMESSAGE FAR * lppEmptyMessage
);
```

## <a name="parameters"></a><span data-ttu-id="c8415-106">参数</span><span class="sxs-lookup"><span data-stu-id="c8415-106">Parameters</span></span>

 <span data-ttu-id="c8415-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c8415-107">_ulFlags_</span></span>
  
> <span data-ttu-id="c8415-108">[in]位掩码的标志，控制如何生成读取或 nonread 的报告。</span><span class="sxs-lookup"><span data-stu-id="c8415-108">[in] A bitmask of flags that controls how the read or nonread report is generated.</span></span> <span data-ttu-id="c8415-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="c8415-109">The following flag can be set:</span></span>
    
<span data-ttu-id="c8415-110">MAPI_NON_READ</span><span class="sxs-lookup"><span data-stu-id="c8415-110">MAPI_NON_READ</span></span> 
  
> <span data-ttu-id="c8415-111">生成 nonread 的报告。</span><span class="sxs-lookup"><span data-stu-id="c8415-111">A nonread report is generated.</span></span> <span data-ttu-id="c8415-112">如果未设置 MAPI_NON_READ，生成读取的报表。</span><span class="sxs-lookup"><span data-stu-id="c8415-112">If MAPI_NON_READ is not set, a read report is generated.</span></span>
    
 <span data-ttu-id="c8415-113">_lpReadMessage_</span><span class="sxs-lookup"><span data-stu-id="c8415-113">_lpReadMessage_</span></span>
  
> <span data-ttu-id="c8415-114">[in]一个指向有关哪些应生成报告的邮件。</span><span class="sxs-lookup"><span data-stu-id="c8415-114">[in] A pointer to the message about which the report should be generated.</span></span>
    
 <span data-ttu-id="c8415-115">_lppEmptyMessage_</span><span class="sxs-lookup"><span data-stu-id="c8415-115">_lppEmptyMessage_</span></span>
  
> <span data-ttu-id="c8415-116">[传入、 传出]在输入_lppEmptyMessage_指向指向空消息的指针。</span><span class="sxs-lookup"><span data-stu-id="c8415-116">[in, out] On input,  _lppEmptyMessage_ points to a pointer to an empty message.</span></span> <span data-ttu-id="c8415-117">输出， _lppEmptyMessage_指向指向报告消息的指针。</span><span class="sxs-lookup"><span data-stu-id="c8415-117">On output,  _lppEmptyMessage_ points to a pointer to the report message.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c8415-118">返回值</span><span class="sxs-lookup"><span data-stu-id="c8415-118">Return value</span></span>

<span data-ttu-id="c8415-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8415-119">S_OK</span></span> 
  
> <span data-ttu-id="c8415-120">成功生成报告。</span><span class="sxs-lookup"><span data-stu-id="c8415-120">The report was successfully generated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c8415-121">注解</span><span class="sxs-lookup"><span data-stu-id="c8415-121">Remarks</span></span>

<span data-ttu-id="c8415-122">只为消息存储提供程序支持对象实现**IMAPISupport::ReadReceipt**方法。</span><span class="sxs-lookup"><span data-stu-id="c8415-122">The **IMAPISupport::ReadReceipt** method is implemented only for message store provider support objects.</span></span> <span data-ttu-id="c8415-123">消息存储提供程序调用**readreceipt 已**以指示 MAPI 生成读取或 nonread 的报告_lpReadMessage_参数指向的邮件。</span><span class="sxs-lookup"><span data-stu-id="c8415-123">Message store providers call **ReadReceipt** to instruct MAPI to generate a read or nonread report for the message pointed to by the  _lpReadMessage_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c8415-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c8415-124">Notes to callers</span></span>

<span data-ttu-id="c8415-125">时设置**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性，而且以下条件之一是，则返回 true，则调用**readreceipt 已**：</span><span class="sxs-lookup"><span data-stu-id="c8415-125">Call **ReadReceipt** when the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property is set and one of the following conditions is true:</span></span>
  
- <span data-ttu-id="c8415-126">邮件已被阅读。</span><span class="sxs-lookup"><span data-stu-id="c8415-126">The message has been read.</span></span>
    
- <span data-ttu-id="c8415-127">邮件已移动。</span><span class="sxs-lookup"><span data-stu-id="c8415-127">The message has been moved.</span></span>
    
- <span data-ttu-id="c8415-128">邮件已复制。</span><span class="sxs-lookup"><span data-stu-id="c8415-128">The message has been copied.</span></span>
    
- <span data-ttu-id="c8415-129">调用了消息的[IMessage::SetReadFlag](imessage-setreadflag.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c8415-129">The message's [IMessage::SetReadFlag](imessage-setreadflag.md) method has been called.</span></span> 
    
<span data-ttu-id="c8415-130">不要调用**readreceipt 已**删除邮件时。</span><span class="sxs-lookup"><span data-stu-id="c8415-130">Do not call **ReadReceipt** when a message is deleted.</span></span> 
  
<span data-ttu-id="c8415-131">为读取或 nonread 的报表应发送仅执行一次邮件。</span><span class="sxs-lookup"><span data-stu-id="c8415-131">A read or nonread report should be sent only once for a message.</span></span> <span data-ttu-id="c8415-132">跟踪的消息的只读的状态，但不会发送单个邮件的多个报表。</span><span class="sxs-lookup"><span data-stu-id="c8415-132">Keep track of a message's read status and do not send multiple reports for a single message.</span></span>
  
<span data-ttu-id="c8415-133">如果_lppEmptyMessage_参数指向有效报告消息 MAPI 返回**readreceipt 已**从时，，呼叫要发送消息，然后通过调用其**IUnknown:s:Release 释放鼠标指针的[IMessage::SubmitMessage](imessage-submitmessage.md)方法**方法。</span><span class="sxs-lookup"><span data-stu-id="c8415-133">If the  _lppEmptyMessage_ parameter points to a valid report message when MAPI returns from **ReadReceipt**, call the [IMessage::SubmitMessage](imessage-submitmessage.md) method to send the message and then release the pointer by calling its **IUnknown:s:Release** method.</span></span> 
  
<span data-ttu-id="c8415-134">如果**readreceipt 已**失败，则应未经要提交释放邮件。</span><span class="sxs-lookup"><span data-stu-id="c8415-134">If **ReadReceipt** fails, the message should be released without being submitted.</span></span> <span data-ttu-id="c8415-135">如果存储消息的只读的状态，您可以尝试在以后生成的已读或 nonread 的报告。</span><span class="sxs-lookup"><span data-stu-id="c8415-135">If you store the message's read status, you can attempt to generate the read or nonread report at a later time.</span></span> 
  
<span data-ttu-id="c8415-136">您可以隐藏或显示生成的文件夹中存储的读取和 nonread 报告。</span><span class="sxs-lookup"><span data-stu-id="c8415-136">You can either hide or display read and nonread reports generated by stores in your folders.</span></span> <span data-ttu-id="c8415-137">隐藏文件夹中存储读取和 nonread 报告使您能够实现更严格的安全性。</span><span class="sxs-lookup"><span data-stu-id="c8415-137">Storing read and nonread reports in hidden folders enables you to implement tighter security.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c8415-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8415-138">See also</span></span>



[<span data-ttu-id="c8415-139">IMAPIFolder::DeleteMessages</span><span class="sxs-lookup"><span data-stu-id="c8415-139">IMAPIFolder::DeleteMessages</span></span>](imapifolder-deletemessages.md)
  
[<span data-ttu-id="c8415-140">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="c8415-140">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="c8415-141">PidTagReadReceiptRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="c8415-141">PidTagReadReceiptRequested Canonical Property</span></span>](pidtagreadreceiptrequested-canonical-property.md)
  
[<span data-ttu-id="c8415-142">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c8415-142">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

