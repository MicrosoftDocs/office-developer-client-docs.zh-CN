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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1915004847fdfd27c97656223866aaab9d3e59c9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326304"
---
# <a name="imapisupportreadreceipt"></a><span data-ttu-id="12afe-103">IMAPISupport::ReadReceipt</span><span class="sxs-lookup"><span data-stu-id="12afe-103">IMAPISupport::ReadReceipt</span></span>

  
  
<span data-ttu-id="12afe-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12afe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="12afe-105">生成邮件的读取或未读报告。</span><span class="sxs-lookup"><span data-stu-id="12afe-105">Generates a read or nonread report for a message.</span></span>
  
```cpp
HRESULT ReadReceipt(
ULONG ulFlags,
LPMESSAGE lpReadMessage,
LPMESSAGE FAR * lppEmptyMessage
);
```

## <a name="parameters"></a><span data-ttu-id="12afe-106">参数</span><span class="sxs-lookup"><span data-stu-id="12afe-106">Parameters</span></span>

 <span data-ttu-id="12afe-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="12afe-107">_ulFlags_</span></span>
  
> <span data-ttu-id="12afe-108">实时标志的位掩码, 用于控制如何生成读取或未读报告。</span><span class="sxs-lookup"><span data-stu-id="12afe-108">[in] A bitmask of flags that controls how the read or nonread report is generated.</span></span> <span data-ttu-id="12afe-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="12afe-109">The following flag can be set:</span></span>
    
<span data-ttu-id="12afe-110">MAPI_NON_READ</span><span class="sxs-lookup"><span data-stu-id="12afe-110">MAPI_NON_READ</span></span> 
  
> <span data-ttu-id="12afe-111">生成未读报告。</span><span class="sxs-lookup"><span data-stu-id="12afe-111">A nonread report is generated.</span></span> <span data-ttu-id="12afe-112">如果未设置 MAPI_NON_READ, 则会生成一个读取报告。</span><span class="sxs-lookup"><span data-stu-id="12afe-112">If MAPI_NON_READ is not set, a read report is generated.</span></span>
    
 <span data-ttu-id="12afe-113">_lpReadMessage_</span><span class="sxs-lookup"><span data-stu-id="12afe-113">_lpReadMessage_</span></span>
  
> <span data-ttu-id="12afe-114">实时指向有关应生成报告的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="12afe-114">[in] A pointer to the message about which the report should be generated.</span></span>
    
 <span data-ttu-id="12afe-115">_lppEmptyMessage_</span><span class="sxs-lookup"><span data-stu-id="12afe-115">_lppEmptyMessage_</span></span>
  
> <span data-ttu-id="12afe-116">[in, out]在输入时, _lppEmptyMessage_指向指向空邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="12afe-116">[in, out] On input,  _lppEmptyMessage_ points to a pointer to an empty message.</span></span> <span data-ttu-id="12afe-117">在输出时, _lppEmptyMessage_指向报告消息的指针。</span><span class="sxs-lookup"><span data-stu-id="12afe-117">On output,  _lppEmptyMessage_ points to a pointer to the report message.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="12afe-118">返回值</span><span class="sxs-lookup"><span data-stu-id="12afe-118">Return value</span></span>

<span data-ttu-id="12afe-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="12afe-119">S_OK</span></span> 
  
> <span data-ttu-id="12afe-120">已成功生成报告。</span><span class="sxs-lookup"><span data-stu-id="12afe-120">The report was successfully generated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="12afe-121">注解</span><span class="sxs-lookup"><span data-stu-id="12afe-121">Remarks</span></span>

<span data-ttu-id="12afe-122">仅对消息存储提供程序支持对象实现**IMAPISupport:: ReadReceipt**方法。</span><span class="sxs-lookup"><span data-stu-id="12afe-122">The **IMAPISupport::ReadReceipt** method is implemented only for message store provider support objects.</span></span> <span data-ttu-id="12afe-123">邮件存储提供程序调用**ReadReceipt**以指示 MAPI 为_lpReadMessage_参数指向的邮件生成读取或未读报告。</span><span class="sxs-lookup"><span data-stu-id="12afe-123">Message store providers call **ReadReceipt** to instruct MAPI to generate a read or nonread report for the message pointed to by the  _lpReadMessage_ parameter.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="12afe-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="12afe-124">Notes to callers</span></span>

<span data-ttu-id="12afe-125">如果设置了**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性, 并且满足以下条件之一, 则调用**ReadReceipt** :</span><span class="sxs-lookup"><span data-stu-id="12afe-125">Call **ReadReceipt** when the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property is set and one of the following conditions is true:</span></span>
  
- <span data-ttu-id="12afe-126">邮件已阅读。</span><span class="sxs-lookup"><span data-stu-id="12afe-126">The message has been read.</span></span>
    
- <span data-ttu-id="12afe-127">邮件已移动。</span><span class="sxs-lookup"><span data-stu-id="12afe-127">The message has been moved.</span></span>
    
- <span data-ttu-id="12afe-128">邮件已复制。</span><span class="sxs-lookup"><span data-stu-id="12afe-128">The message has been copied.</span></span>
    
- <span data-ttu-id="12afe-129">已调用邮件的[IMessage:: SetReadFlag](imessage-setreadflag.md)方法。</span><span class="sxs-lookup"><span data-stu-id="12afe-129">The message's [IMessage::SetReadFlag](imessage-setreadflag.md) method has been called.</span></span> 
    
<span data-ttu-id="12afe-130">删除邮件时不要调用**ReadReceipt** 。</span><span class="sxs-lookup"><span data-stu-id="12afe-130">Do not call **ReadReceipt** when a message is deleted.</span></span> 
  
<span data-ttu-id="12afe-131">对于一条消息, 应仅向其发送一次 read 或未读报告。</span><span class="sxs-lookup"><span data-stu-id="12afe-131">A read or nonread report should be sent only once for a message.</span></span> <span data-ttu-id="12afe-132">跟踪邮件的阅读状态, 并且不发送单个邮件的多个报告。</span><span class="sxs-lookup"><span data-stu-id="12afe-132">Keep track of a message's read status and do not send multiple reports for a single message.</span></span>
  
<span data-ttu-id="12afe-133">如果 MAPI 从**ReadReceipt**返回时, 如果_lppEmptyMessage_参数指向有效的报告消息, 请调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法以发送邮件, 然后通过调用其 IUnknown 来释放指针 **: s: release**方法。</span><span class="sxs-lookup"><span data-stu-id="12afe-133">If the  _lppEmptyMessage_ parameter points to a valid report message when MAPI returns from **ReadReceipt**, call the [IMessage::SubmitMessage](imessage-submitmessage.md) method to send the message and then release the pointer by calling its **IUnknown:s:Release** method.</span></span> 
  
<span data-ttu-id="12afe-134">如果**ReadReceipt**失败, 应在不提交邮件的情况下释放邮件。</span><span class="sxs-lookup"><span data-stu-id="12afe-134">If **ReadReceipt** fails, the message should be released without being submitted.</span></span> <span data-ttu-id="12afe-135">如果您存储邮件的阅读状态, 则可以尝试在以后生成 read 或未读报告。</span><span class="sxs-lookup"><span data-stu-id="12afe-135">If you store the message's read status, you can attempt to generate the read or nonread report at a later time.</span></span> 
  
<span data-ttu-id="12afe-136">您可以隐藏或显示由文件夹中的存储生成的已读和未读报告。</span><span class="sxs-lookup"><span data-stu-id="12afe-136">You can either hide or display read and nonread reports generated by stores in your folders.</span></span> <span data-ttu-id="12afe-137">在隐藏文件夹中存储读取和未读报告使您能够实现更严格的安全性。</span><span class="sxs-lookup"><span data-stu-id="12afe-137">Storing read and nonread reports in hidden folders enables you to implement tighter security.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="12afe-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12afe-138">See also</span></span>



[<span data-ttu-id="12afe-139">IMAPIFolder::DeleteMessages</span><span class="sxs-lookup"><span data-stu-id="12afe-139">IMAPIFolder::DeleteMessages</span></span>](imapifolder-deletemessages.md)
  
[<span data-ttu-id="12afe-140">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="12afe-140">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="12afe-141">PidTagReadReceiptRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="12afe-141">PidTagReadReceiptRequested Canonical Property</span></span>](pidtagreadreceiptrequested-canonical-property.md)
  
[<span data-ttu-id="12afe-142">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="12afe-142">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

