---
title: 跟踪对话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0500dee8-a39d-45ce-87b1-c515e92e083d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7f1dd7a23bbd643b496b7634b6ad0230c806585f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398603"
---
# <a name="tracking-conversations"></a><span data-ttu-id="ecb3e-103">跟踪对话</span><span class="sxs-lookup"><span data-stu-id="ecb3e-103">Tracking Conversations</span></span>

  
  
<span data-ttu-id="ecb3e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ecb3e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ecb3e-105">对话跟踪正在收集 エ ・ 复 ハ 一条消息。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-105">Conversation tracking is collecting responses to a message.</span></span> <span data-ttu-id="ecb3e-106">客户端应在跟踪对话设置帮助的两个属性：</span><span class="sxs-lookup"><span data-stu-id="ecb3e-106">Clients should set two properties that aid in tracking conversations:</span></span>
  
- <span data-ttu-id="ecb3e-107">**PR_CONVERSATION_TOPIC**([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ecb3e-107">**PR_CONVERSATION_TOPIC** ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))</span></span>
    
    <span data-ttu-id="ecb3e-108">**PR_CONVERSATION_TOPIC**是规范化的邮件的主题，没有前缀字符串主题。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-108">**PR_CONVERSATION_TOPIC** is the normalized subject of the message, the subject without the prefix strings.</span></span> <span data-ttu-id="ecb3e-109">将此属性设置为消息的**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-109">Set this property to the value of the message's **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) property.</span></span> 
    
- <span data-ttu-id="ecb3e-110">**PR_CONVERSATION_INDEX**([PidTagConversationIndex](pidtagconversationindex-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ecb3e-110">**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md))</span></span>
    
    <span data-ttu-id="ecb3e-111">**PR_CONVERSATION_INDEX**指示特定的对话中的邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-111">**PR_CONVERSATION_INDEX** indicates the position of the message within a particular conversation.</span></span> <span data-ttu-id="ecb3e-112">新的邮件、 转发的邮件或回复是否是客户端的 reponsibility **PR_CONVERSATION_INDEX**设置为每个传出消息。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-112">It is a client's reponsibility to set **PR_CONVERSATION_INDEX** for each outgoing message, whether it is a new message, a forwarded message, or a reply.</span></span> <span data-ttu-id="ecb3e-113">客户端可以手动设置此属性，或者调用[ScCreateConversationIndex](sccreateconversationindex.md)，MAPI 提供的实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-113">Clients can set this property manually or call [ScCreateConversationIndex](sccreateconversationindex.md), a utility function provided by MAPI.</span></span> 
    
 <span data-ttu-id="ecb3e-114">**ScCreateConversationIndex**生成任何传出消息的对话索引的值。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-114">**ScCreateConversationIndex** generates the value of a conversation index for any outgoing message.</span></span> <span data-ttu-id="ecb3e-115">**ScCreateConversationIndex**实现索引作为标头块的 22 字节的长度后, 跟零个或更多的子阻止在长度每 5 个字节。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-115">**ScCreateConversationIndex** implements the index as a header block that is 22 bytes in length, followed by zero or more child blocks each 5 bytes in length.</span></span> 
  
<span data-ttu-id="ecb3e-116">标头块组成 22 字节，分为三个部分：</span><span class="sxs-lookup"><span data-stu-id="ecb3e-116">The header block is composed of 22 bytes, divided into three parts:</span></span>
  
- <span data-ttu-id="ecb3e-117">一个保留的字节。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-117">One reserved byte.</span></span> <span data-ttu-id="ecb3e-118">其值为 1。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-118">Its value is 1.</span></span>
    
- <span data-ttu-id="ecb3e-119">五个字节用于当前系统时间转换为[FILETIME](filetime.md)结构格式。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-119">Five bytes for the current system time converted to the [FILETIME](filetime.md) structure format.</span></span> 
    
- <span data-ttu-id="ecb3e-120">16 个字节保留的[GUID](guid.md)或全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-120">Sixteen bytes holding a [GUID](guid.md), or globally unique identifier.</span></span>
    
<span data-ttu-id="ecb3e-121">每个子块组成 5 个字节，划分，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ecb3e-121">Each child block is composed of 5 bytes, divided as follows:</span></span>
  
- <span data-ttu-id="ecb3e-122">包含表示当前时间和存储在标头块的时间之间的差异的代码的一位。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-122">One bit containing a code representing the difference between the current time and the time stored in the header block.</span></span> <span data-ttu-id="ecb3e-123">如果差不超过.02 第二个和大于两年和 1 如果差小于一秒 56 年以上，则此位将为 0。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-123">This bit will be 0 if the difference is less than .02 second and greater than two years and 1 if the difference is less than one second and greater than 56 years.</span></span>
    
- <span data-ttu-id="ecb3e-124">包含以**FILETIME**单位表示的标头块中的当前时间与完成时间之间的区别三十一位。子块的这一部分将生成使用两种策略，具体取决于第一位的值之一。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-124">Thirty one bits containing the difference between the current time and the time in the header block expressed in **FILETIME** units.This part of the child block is produced using one of two strategies, depending on the value of the first bit.</span></span> <span data-ttu-id="ecb3e-125">如果此位为零， **ScCreateConversationIndex**放弃高 15 位和低 18 位。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-125">If this bit is zero, **ScCreateConversationIndex** discards the high 15 bits and the low 18 bits.</span></span> <span data-ttu-id="ecb3e-126">如果此位是一个，该函数将丢弃高 10 位和低 23 位。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-126">If this bit is one, the function discards the high 10 bits and the low 23 bits.</span></span> 
    
- <span data-ttu-id="ecb3e-127">包含通过调用 Win32 函数[GetTickCount](https://msdn.microsoft.com/library/ms724408%28VS.85%29.aspx)生成一个随机数字的四位。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-127">Four bits containing a random number generated by calling the Win32 function [GetTickCount](https://msdn.microsoft.com/library/ms724408%28VS.85%29.aspx).</span></span>
    
- <span data-ttu-id="ecb3e-128">包含一系列的四位计数的取自随机数字的一部分。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-128">Four bits containing a sequence count that is taken from part of the random number.</span></span>
    
<span data-ttu-id="ecb3e-129">如果您选择手动设置消息的对话索引，请考虑以下建议：</span><span class="sxs-lookup"><span data-stu-id="ecb3e-129">If you choose to set the conversation indexes of messages manually, consider the following suggestions:</span></span>
  
1. <span data-ttu-id="ecb3e-130">保留透明; 响应者时区的差异使用 UTC 时间，而不是本地时间。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-130">Keep differences in the respondents' time zones transparent; use UTC times rather than local time.</span></span>
    
2. <span data-ttu-id="ecb3e-131">通过了相同时间缩进每个对话组。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-131">Indent each conversation group by the same amount.</span></span>
    
3. <span data-ttu-id="ecb3e-132">排序 エ ・ 复 ハ 相同的消息日期。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-132">Sort responses to the same message date.</span></span>
    
4. <span data-ttu-id="ecb3e-133">在发生共享相同的主题的不同时间开始的单独的线程。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-133">Separate threads started at different times that happen to share the same topic.</span></span> 
    
5. <span data-ttu-id="ecb3e-134">若要实现分类的排序，以便按主题分组消息，排序按**PR_CONVERSATION_TOPIC**第一个，然后按**PR_CONVERSATION_INDEX**。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-134">To implement a categorized sort so that messages are grouped by topic, sort by **PR_CONVERSATION_TOPIC** first and then by **PR_CONVERSATION_INDEX**.</span></span> <span data-ttu-id="ecb3e-135">显示排序的结果，设置为 0 邮件是在长度 22 字节的对话索引**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-135">To present the results of the sort, set the **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) property to 0 for messages with a conversation index that is 22 bytes in length.</span></span> <span data-ttu-id="ecb3e-136">然后，在长度每 5 字节增量，增加**PR_DEPTH**属性的值 1。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-136">Then, for every 5-byte increment in the length, increment the value of the **PR_DEPTH** property by one.</span></span> 
    
<span data-ttu-id="ecb3e-137">PR_ORIGINAL 组属性还可用于跟踪的对话。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-137">The PR_ORIGINAL group of properties can also be used for conversation tracking.</span></span> <span data-ttu-id="ecb3e-138">设置这些属性以链接到原始邮件的答复或转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-138">Set these properties to link reply or forwarded messages to the original message.</span></span> <span data-ttu-id="ecb3e-139">所有 PR_ORIGINAL 属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-139">All of the PR_ORIGINAL properties are optional.</span></span> <span data-ttu-id="ecb3e-140">如果您未显式设置，例如， **PR_ORIGINAL_AUTHOR_ENTRYID** ([PidTagOriginalAuthorEntryId](pidtagoriginalauthorentryid-canonical-property.md)) 的消息存储提供程序可以使用默认值或**PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 的值属性。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-140">If you do not explicitly set, for example, **PR_ORIGINAL_AUTHOR_ENTRYID** ([PidTagOriginalAuthorEntryId](pidtagoriginalauthorentryid-canonical-property.md)), the message store provider can use the default value, or the value of the **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="ecb3e-141">同样，如果未设置**PR_ORIGINAL_AUTHOR_NAME**或**PR_ORIGINAL_SUBMIT_TIME** ([PidTagOriginalSubmitTime](pidtagoriginalsubmittime-canonical-property.md))，这些属性可以使用默认**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 和**PR_ 的值CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性，分别。</span><span class="sxs-lookup"><span data-stu-id="ecb3e-141">Likewise, if you do not set **PR_ORIGINAL_AUTHOR_NAME** or **PR_ORIGINAL_SUBMIT_TIME** ([PidTagOriginalSubmitTime](pidtagoriginalsubmittime-canonical-property.md)), these properties can default to the values of the **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) and **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) properties, respectively.</span></span> 
  

