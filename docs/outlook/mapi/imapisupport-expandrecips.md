---
title: IMAPISupportExpandRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ExpandRecips
api_type:
- COM
ms.assetid: 78edd549-d557-489a-85f5-adfb5c44a7d4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 105219fe430cd8746c3aa6cf5cd90629d5f72080
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411244"
---
# <a name="imapisupportexpandrecips"></a><span data-ttu-id="a5697-103">IMAPISupport::ExpandRecips</span><span class="sxs-lookup"><span data-stu-id="a5697-103">IMAPISupport::ExpandRecips</span></span>

  
  
<span data-ttu-id="a5697-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a5697-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a5697-105">完成邮件的收件人列表，扩展特定通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="a5697-105">Completes a message's recipient list, expanding particular distribution lists.</span></span>
  
```cpp
HRESULT ExpandRecips(
  LPMESSAGE lpMessage,
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="a5697-106">参数</span><span class="sxs-lookup"><span data-stu-id="a5697-106">Parameters</span></span>

 <span data-ttu-id="a5697-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="a5697-107">_lpMessage_</span></span>
  
> <span data-ttu-id="a5697-108">[in]指向包含要处理的收件人列表的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="a5697-108">[in] A pointer to the message that has the recipient list to be processed.</span></span>
    
 <span data-ttu-id="a5697-109">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="a5697-109">_lpulFlags_</span></span>
  
> <span data-ttu-id="a5697-110">[out]指向控制所发生处理类型的标志的位掩码的指针。</span><span class="sxs-lookup"><span data-stu-id="a5697-110">[out] A pointer to a bitmask of flags that controls the type of processing that occurs.</span></span> <span data-ttu-id="a5697-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a5697-111">The following flags can be set:</span></span>
    
<span data-ttu-id="a5697-112">NEEDS_PREPROCESSING</span><span class="sxs-lookup"><span data-stu-id="a5697-112">NEEDS_PREPROCESSING</span></span> 
  
> <span data-ttu-id="a5697-113">在发送邮件之前，需要先对邮件进行预处理。</span><span class="sxs-lookup"><span data-stu-id="a5697-113">The message needs to be preprocessed before it is sent.</span></span>
    
<span data-ttu-id="a5697-114">NEEDS_SPOOLER</span><span class="sxs-lookup"><span data-stu-id="a5697-114">NEEDS_SPOOLER</span></span> 
  
> <span data-ttu-id="a5697-115">MAPI 后台处理程序 (与呼叫者紧密耦合的传输提供程序) 必须发送邮件。</span><span class="sxs-lookup"><span data-stu-id="a5697-115">The MAPI spooler (rather than the transport provider to which the caller is tightly coupled) must send the message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a5697-116">返回值</span><span class="sxs-lookup"><span data-stu-id="a5697-116">Return value</span></span>

<span data-ttu-id="a5697-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5697-117">S_OK</span></span> 
  
> <span data-ttu-id="a5697-118">已成功处理邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="a5697-118">The message's recipient list was successfully processed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a5697-119">备注</span><span class="sxs-lookup"><span data-stu-id="a5697-119">Remarks</span></span>

<span data-ttu-id="a5697-120">**IMAPISupport：：ExpandRecips** 方法为邮件存储提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="a5697-120">The **IMAPISupport::ExpandRecips** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="a5697-121">邮件存储提供程序调用 **ExpandRecips** 以提示 MAPI 执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a5697-121">Message store providers call **ExpandRecips** to prompt MAPI to perform the following tasks:</span></span> 
  
- <span data-ttu-id="a5697-122">将某些个人通讯组列表展开到其组件收件人。</span><span class="sxs-lookup"><span data-stu-id="a5697-122">Expand certain personal distribution lists to their component recipients.</span></span>
    
- <span data-ttu-id="a5697-123">将已更改的所有显示名称替换为原始名称。</span><span class="sxs-lookup"><span data-stu-id="a5697-123">Replace all display names that have been changed with the original names.</span></span>
    
- <span data-ttu-id="a5697-124">标记任何重复的条目。</span><span class="sxs-lookup"><span data-stu-id="a5697-124">Mark any duplicate entries.</span></span>
    
- <span data-ttu-id="a5697-125">解析所有一次地址。</span><span class="sxs-lookup"><span data-stu-id="a5697-125">Resolve all one-off addresses.</span></span> 
    
- <span data-ttu-id="a5697-126">检查邮件是否需要预处理，如果需要预处理，则设置  _lpulFlags_ 指向NEEDS_PREPROCESSING。</span><span class="sxs-lookup"><span data-stu-id="a5697-126">Check whether the message needs preprocessing and, if it does, set the flag pointed to by  _lpulFlags_ to NEEDS_PREPROCESSING.</span></span> 
    
 <span data-ttu-id="a5697-127">**ExpandRecips** 展开邮件地址类型为 MAPIPDL 的任何通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="a5697-127">**ExpandRecips** expands any distribution lists that have the messaging address type of MAPIPDL.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="a5697-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a5697-128">Notes to callers</span></span>

<span data-ttu-id="a5697-129">始终在 **邮件处理过程中调用 ExpandRecips。**</span><span class="sxs-lookup"><span data-stu-id="a5697-129">Always call **ExpandRecips** as part of your message processing.</span></span> <span data-ttu-id="a5697-130">调用 **ExpandRecips，** 这是 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法实现中的第一个调用。</span><span class="sxs-lookup"><span data-stu-id="a5697-130">Make a call to **ExpandRecips** one of the first calls in your [IMessage::SubmitMessage](imessage-submitmessage.md) method implementation.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a5697-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5697-131">See also</span></span>



[<span data-ttu-id="a5697-132">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="a5697-132">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="a5697-133">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a5697-133">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

