---
title: 跟踪对话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
api_type:
- COM
ms.assetid: 0500dee8-a39d-45ce-87b1-c515e92e083d
description: 上次修改时间：2011 年 7 月 23 日
localization_priority: Priority
ms.openlocfilehash: 3a59a7a15b4647832634adc4757544876b8841b1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349544"
---
# <a name="tracking-conversations"></a><span data-ttu-id="a994a-103">跟踪对话</span><span class="sxs-lookup"><span data-stu-id="a994a-103">Tracking Conversations</span></span>

  
  
<span data-ttu-id="a994a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a994a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a994a-105">对话跟踪收集邮件响应。</span><span class="sxs-lookup"><span data-stu-id="a994a-105">Conversation tracking is collecting responses to a message.</span></span> <span data-ttu-id="a994a-106">客户应设置以下两个属性，以辅助跟踪对话：</span><span class="sxs-lookup"><span data-stu-id="a994a-106">Clients should set two properties that aid in tracking conversations:</span></span>
  
- <span data-ttu-id="a994a-107">**PR_CONVERSATION_TOPIC** ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a994a-107">**PR_CONVERSATION_TOPIC** ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))</span></span>
    
    <span data-ttu-id="a994a-108">**PR_CONVERSATION_TOPIC** 是邮件的标准化主题，该主题没有前缀字符串。</span><span class="sxs-lookup"><span data-stu-id="a994a-108">**PR_CONVERSATION_TOPIC** is the normalized subject of the message, the subject without the prefix strings.</span></span> <span data-ttu-id="a994a-109">将此属性设为邮件的 **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 属性值。</span><span class="sxs-lookup"><span data-stu-id="a994a-109">Set this property to the value of the message's **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) property.</span></span> 
    
- <span data-ttu-id="a994a-110">**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a994a-110">**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md))</span></span>
    
    <span data-ttu-id="a994a-111">**PR_CONVERSATION_INDEX** 指示邮件在特定对话中的位置。</span><span class="sxs-lookup"><span data-stu-id="a994a-111">**PR_CONVERSATION_INDEX** indicates the position of the message within a particular conversation.</span></span> <span data-ttu-id="a994a-112">客户有责任为每个传出邮件设置 **PR_CONVERSATION_INDEX**，无论它是新邮件、转发邮件还是回复邮件。</span><span class="sxs-lookup"><span data-stu-id="a994a-112">It is a client's reponsibility to set **PR_CONVERSATION_INDEX** for each outgoing message, whether it is a new message, a forwarded message, or a reply.</span></span> <span data-ttu-id="a994a-113">客户可以手动设置此属性或调用 MAPI 提供的实用程序函数 [ScCreateConversationIndex](sccreateconversationindex.md)。</span><span class="sxs-lookup"><span data-stu-id="a994a-113">Clients can set this property manually or call [ScCreateConversationIndex](sccreateconversationindex.md), a utility function provided by MAPI.</span></span> 
    
 <span data-ttu-id="a994a-114">**ScCreateConversationIndex** 将为任何传出邮件生成对话索引值。</span><span class="sxs-lookup"><span data-stu-id="a994a-114">**ScCreateConversationIndex** generates the value of a conversation index for any outgoing message.</span></span> <span data-ttu-id="a994a-115">**ScCreateConversationIndex** 将索引用作页眉构建基块，该基块长度为 22 字节，后跟 0 个或多个长度为 5 字节的子基块。</span><span class="sxs-lookup"><span data-stu-id="a994a-115">**ScCreateConversationIndex** implements the index as a header block that is 22 bytes in length, followed by zero or more child blocks each 5 bytes in length.</span></span> 
  
<span data-ttu-id="a994a-116">页眉构建基块由 22 字节组成，分成三个部分：</span><span class="sxs-lookup"><span data-stu-id="a994a-116">The header block is composed of 22 bytes, divided into three parts:</span></span>
  
- <span data-ttu-id="a994a-117">一个保留字节。</span><span class="sxs-lookup"><span data-stu-id="a994a-117">One reserved byte.</span></span> <span data-ttu-id="a994a-118">其值为 1。</span><span class="sxs-lookup"><span data-stu-id="a994a-118">Its value is 1.</span></span>
    
- <span data-ttu-id="a994a-119">5 字节用于当前系统时间，该时间转换为 [FILETIME](filetime.md) 结构格式。</span><span class="sxs-lookup"><span data-stu-id="a994a-119">Five bytes for the current system time converted to the [FILETIME](filetime.md) structure format.</span></span> 
    
- <span data-ttu-id="a994a-120">16 个字节用于保留 [GUID](guid.md)，或全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a994a-120">Sixteen bytes holding a [GUID](guid.md), or globally unique identifier.</span></span>
    
<span data-ttu-id="a994a-121">每个子基块由 5 字节组成，分成以下部分：</span><span class="sxs-lookup"><span data-stu-id="a994a-121">Each child block is composed of 5 bytes, divided as follows:</span></span>
  
- <span data-ttu-id="a994a-122">1 位包含表示当前时间与页眉构建基块中存储的时间之间的差异的代码。</span><span class="sxs-lookup"><span data-stu-id="a994a-122">One bit containing a code representing the difference between the current time and the time stored in the header block.</span></span> <span data-ttu-id="a994a-123">如果差异小于 0.02 秒且大于 2 年，则此位为 0，如果差异小于 1 秒且大于 56 年，则为 1。</span><span class="sxs-lookup"><span data-stu-id="a994a-123">This bit will be 0 if the difference is less than .02 second and greater than two years and 1 if the difference is less than one second and greater than 56 years.</span></span>
    
- <span data-ttu-id="a994a-124">31 位包含当前时间和页眉构建基块中的时间（以 **FILETIME** 单位表示）之间的差异。子基块的这个部分是通过两种战略之一生成，具体取决于第一位的值。</span><span class="sxs-lookup"><span data-stu-id="a994a-124">Thirty one bits containing the difference between the current time and the time in the header block expressed in **FILETIME** units.This part of the child block is produced using one of two strategies, depending on the value of the first bit.</span></span> <span data-ttu-id="a994a-125">如果此位为 0，则 **ScCreateConversationIndex** 将丢弃高 15 位和低 18 位。</span><span class="sxs-lookup"><span data-stu-id="a994a-125">If this bit is zero, **ScCreateConversationIndex** discards the high 15 bits and the low 18 bits.</span></span> <span data-ttu-id="a994a-126">如果此位为 1，则函数将丢弃高 10 位和低 23 位。</span><span class="sxs-lookup"><span data-stu-id="a994a-126">If this bit is one, the function discards the high 10 bits and the low 23 bits.</span></span> 
    
- <span data-ttu-id="a994a-127">4 位包含调用 Win32 函数 [GetTickCount](https://msdn.microsoft.com/library/ms724408%28VS.85%29.aspx) 所生成的随机数字。</span><span class="sxs-lookup"><span data-stu-id="a994a-127">Four bits containing a random number generated by calling the Win32 function [GetTickCount](https://msdn.microsoft.com/library/ms724408%28VS.85%29.aspx).</span></span>
    
- <span data-ttu-id="a994a-128">4 位包含取自随机数字的序列计数。</span><span class="sxs-lookup"><span data-stu-id="a994a-128">Four bits containing a sequence count that is taken from part of the random number.</span></span>
    
<span data-ttu-id="a994a-129">如果选择手动设置邮件索引，请考虑以下建议：</span><span class="sxs-lookup"><span data-stu-id="a994a-129">If you choose to set the conversation indexes of messages manually, consider the following suggestions:</span></span>
  
1. <span data-ttu-id="a994a-130">保持回复者的时区差异透明；使用 UTC 时间而不是本地时间。</span><span class="sxs-lookup"><span data-stu-id="a994a-130">Keep differences in the respondents' time zones transparent; use UTC times rather than local time.</span></span>
    
2. <span data-ttu-id="a994a-131">将每个对话组缩进相同的量。</span><span class="sxs-lookup"><span data-stu-id="a994a-131">Indent each conversation group by the same amount.</span></span>
    
3. <span data-ttu-id="a994a-132">对属于相同邮件日期的回复进行排序。</span><span class="sxs-lookup"><span data-stu-id="a994a-132">Sort responses to the same message date.</span></span>
    
4. <span data-ttu-id="a994a-133">将共用相同主题且从不同时间开始的线程分开。</span><span class="sxs-lookup"><span data-stu-id="a994a-133">Separate threads started at different times that happen to share the same topic.</span></span> 
    
5. <span data-ttu-id="a994a-134">若要通过按类别排序以便按主题对邮件进行分许，请依次按 **PR_CONVERSATION_TOPIC** 和 **PR_CONVERSATION_INDEX** 进行排序。</span><span class="sxs-lookup"><span data-stu-id="a994a-134">To implement a categorized sort so that messages are grouped by topic, sort by **PR_CONVERSATION_TOPIC** first and then by **PR_CONVERSATION_INDEX**.</span></span> <span data-ttu-id="a994a-135">若要展现排序结果，请将对话索引长度为 22 字节的邮件的 **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性设为 0。</span><span class="sxs-lookup"><span data-stu-id="a994a-135">To present the results of the sort, set the **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) property to 0 for messages with a conversation index that is 22 bytes in length.</span></span> <span data-ttu-id="a994a-136">若要实现每次 5 字节的长度增量，请将 **PR_DEPTH** 属性的值增加 1。</span><span class="sxs-lookup"><span data-stu-id="a994a-136">Then, for every 5-byte increment in the length, increment the value of the **PR_DEPTH** property by one.</span></span> 
    
<span data-ttu-id="a994a-137">PR_ORIGINAL 属性组也可用于对话跟踪。</span><span class="sxs-lookup"><span data-stu-id="a994a-137">The PR_ORIGINAL group of properties can also be used for conversation tracking.</span></span> <span data-ttu-id="a994a-138">设置这些属性可将回复邮件或转发邮件链接至原始邮件。</span><span class="sxs-lookup"><span data-stu-id="a994a-138">Set these properties to link reply or forwarded messages to the original message.</span></span> <span data-ttu-id="a994a-139">所有 PR_ORIGINAL 属性均为可选项。</span><span class="sxs-lookup"><span data-stu-id="a994a-139">All of the PR_ORIGINAL properties are optional.</span></span> <span data-ttu-id="a994a-140">例如，如未显式设置 **PR_ORIGINAL_AUTHOR_ENTRYID** ([PidTagOriginalAuthorEntryId](pidtagoriginalauthorentryid-canonical-property.md))，则邮件存储提供程序可使用默认值，或 **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="a994a-140">If you do not explicitly set, for example, **PR_ORIGINAL_AUTHOR_ENTRYID** ([PidTagOriginalAuthorEntryId](pidtagoriginalauthorentryid-canonical-property.md)), the message store provider can use the default value, or the value of the **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="a994a-141">同样，如未设置 **PR_ORIGINAL_AUTHOR_NAME** 或 **PR_ORIGINAL_SUBMIT_TIME** ([PidTagOriginalSubmitTime](pidtagoriginalsubmittime-canonical-property.md))，则这些可默认分别采用 **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 和 **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="a994a-141">Likewise, if you do not set **PR_ORIGINAL_AUTHOR_NAME** or **PR_ORIGINAL_SUBMIT_TIME** ([PidTagOriginalSubmitTime](pidtagoriginalsubmittime-canonical-property.md)), these properties can default to the values of the **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) and **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) properties, respectively.</span></span> 
  

