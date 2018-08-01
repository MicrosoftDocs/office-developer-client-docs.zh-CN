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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2e41701d3a739864b1eafc8001833b7df5c8908b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775614"
---
# <a name="imapisupportexpandrecips"></a><span data-ttu-id="7551f-103">IMAPISupport::ExpandRecips</span><span class="sxs-lookup"><span data-stu-id="7551f-103">IMAPISupport::ExpandRecips</span></span>

  
  
<span data-ttu-id="7551f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7551f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7551f-105">完成邮件的收件人列表中，展开特定的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="7551f-105">Completes a message's recipient list, expanding particular distribution lists.</span></span>
  
```cpp
HRESULT ExpandRecips(
  LPMESSAGE lpMessage,
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="7551f-106">参数</span><span class="sxs-lookup"><span data-stu-id="7551f-106">Parameters</span></span>

 <span data-ttu-id="7551f-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="7551f-107">_lpMessage_</span></span>
  
> <span data-ttu-id="7551f-108">[in]一个指向其处理的收件人列表的邮件。</span><span class="sxs-lookup"><span data-stu-id="7551f-108">[in] A pointer to the message that has the recipient list to be processed.</span></span>
    
 <span data-ttu-id="7551f-109">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="7551f-109">_lpulFlags_</span></span>
  
> <span data-ttu-id="7551f-110">[输出]指向控制，发生此事件的处理的类型的标志位掩码的指针。</span><span class="sxs-lookup"><span data-stu-id="7551f-110">[out] A pointer to a bitmask of flags that controls the type of processing that occurs.</span></span> <span data-ttu-id="7551f-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="7551f-111">The following flags can be set:</span></span>
    
<span data-ttu-id="7551f-112">NEEDS_PREPROCESSING</span><span class="sxs-lookup"><span data-stu-id="7551f-112">NEEDS_PREPROCESSING</span></span> 
  
> <span data-ttu-id="7551f-113">需要发送之前预处理消息。</span><span class="sxs-lookup"><span data-stu-id="7551f-113">The message needs to be preprocessed before it is sent.</span></span>
    
<span data-ttu-id="7551f-114">NEEDS_SPOOLER</span><span class="sxs-lookup"><span data-stu-id="7551f-114">NEEDS_SPOOLER</span></span> 
  
> <span data-ttu-id="7551f-115">MAPI 后台处理程序 （而不是指紧密耦合呼叫者的传输提供程序） 必须发送邮件。</span><span class="sxs-lookup"><span data-stu-id="7551f-115">The MAPI spooler (rather than the transport provider to which the caller is tightly coupled) must send the message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7551f-116">返回值</span><span class="sxs-lookup"><span data-stu-id="7551f-116">Return value</span></span>

<span data-ttu-id="7551f-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="7551f-117">S_OK</span></span> 
  
> <span data-ttu-id="7551f-118">已成功处理邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="7551f-118">The message's recipient list was successfully processed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7551f-119">说明</span><span class="sxs-lookup"><span data-stu-id="7551f-119">Remarks</span></span>

<span data-ttu-id="7551f-120">消息存储提供程序支持对象的实现**IMAPISupport::ExpandRecips**方法。</span><span class="sxs-lookup"><span data-stu-id="7551f-120">The **IMAPISupport::ExpandRecips** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="7551f-121">消息存储提供程序调用**ExpandRecips**提示 MAPI 以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="7551f-121">Message store providers call **ExpandRecips** to prompt MAPI to perform the following tasks:</span></span> 
  
- <span data-ttu-id="7551f-122">展开至其组件收件人的特定个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="7551f-122">Expand certain personal distribution lists to their component recipients.</span></span>
    
- <span data-ttu-id="7551f-123">原始名称中替换所有已更改的显示名称。</span><span class="sxs-lookup"><span data-stu-id="7551f-123">Replace all display names that have been changed with the original names.</span></span>
    
- <span data-ttu-id="7551f-124">标记任何重复项。</span><span class="sxs-lookup"><span data-stu-id="7551f-124">Mark any duplicate entries.</span></span>
    
- <span data-ttu-id="7551f-125">解决所有一次性地址。</span><span class="sxs-lookup"><span data-stu-id="7551f-125">Resolve all one-off addresses.</span></span> 
    
- <span data-ttu-id="7551f-126">检查是否消息需要预处理，并且，如果是这样，设置所指的_lpulFlags_到 NEEDS_PREPROCESSING 标志。</span><span class="sxs-lookup"><span data-stu-id="7551f-126">Check whether the message needs preprocessing and, if it does, set the flag pointed to by  _lpulFlags_ to NEEDS_PREPROCESSING.</span></span> 
    
 <span data-ttu-id="7551f-127">**ExpandRecips**展开具有消息地址类型 MAPIPDL 的任何通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="7551f-127">**ExpandRecips** expands any distribution lists that have the messaging address type of MAPIPDL.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="7551f-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7551f-128">Notes to callers</span></span>

<span data-ttu-id="7551f-129">始终调用**ExpandRecips**作为消息处理的一部分。</span><span class="sxs-lookup"><span data-stu-id="7551f-129">Always call **ExpandRecips** as part of your message processing.</span></span> <span data-ttu-id="7551f-130">在您[IMessage::SubmitMessage](imessage-submitmessage.md)方法实现中进行调用**ExpandRecips**之一的第一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="7551f-130">Make a call to **ExpandRecips** one of the first calls in your [IMessage::SubmitMessage](imessage-submitmessage.md) method implementation.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7551f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7551f-131">See also</span></span>



[<span data-ttu-id="7551f-132">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="7551f-132">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="7551f-133">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7551f-133">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

