---
title: 同步文本和格式设置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d7e166f0-1214-4571-b9a8-366960772a7a
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 40d7a45ab97e0d2f8e9d3db1e1d38eb3bdb75158
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778956"
---
# <a name="synchronizing-text-and-formatting"></a><span data-ttu-id="60c1a-103">同步文本和格式设置</span><span class="sxs-lookup"><span data-stu-id="60c1a-103">Synchronizing Text and Formatting</span></span>

  
  
<span data-ttu-id="60c1a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="60c1a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="60c1a-105">发送富文本格式 (RTF) 邮件的主要难题保持同步带格式的文本。</span><span class="sxs-lookup"><span data-stu-id="60c1a-105">The main challenge in sending Rich Text Format (RTF) messages is keeping the text synchronized with the formatting.</span></span> <span data-ttu-id="60c1a-106">若要确保时邮件到达其目标它们以适合其原始发件人和文本和格式的同步、 MAPI 提供了[RTFSync](rtfsync.md)函数。</span><span class="sxs-lookup"><span data-stu-id="60c1a-106">To ensure that when messages arrive at their destination they are as their originators intended and that the text and formatting are synchronized, MAPI provides the [RTFSync](rtfsync.md) function.</span></span> <span data-ttu-id="60c1a-107">**RTFSync**通常调用之前显示传入消息的 RTF 感知客户端和 MAPI 后台处理程序时其下载到传输提供程序的消息。</span><span class="sxs-lookup"><span data-stu-id="60c1a-107">**RTFSync** is typically called by RTF-aware clients before displaying incoming messages and by the MAPI spooler when it downloads messages to a transport provider.</span></span> <span data-ttu-id="60c1a-108">呼叫者通过将一个或两个标志传递给**RTFSync**指定可能的区别的区域：</span><span class="sxs-lookup"><span data-stu-id="60c1a-108">Callers specify the area of possible discrepancy by passing one or two flags to **RTFSync**:</span></span>
  
- <span data-ttu-id="60c1a-109">指示消息文本中的修改的 RTF_SYNC_BODY_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="60c1a-109">RTF_SYNC_BODY_CHANGED to indicate a modification in message text.</span></span>
    
- <span data-ttu-id="60c1a-110">RTF_SYNC_RTF_CHANGED 以指示邮件格式中的修改。</span><span class="sxs-lookup"><span data-stu-id="60c1a-110">RTF_SYNC_RTF_CHANGED to indicate a modification in message formatting.</span></span>
    
<span data-ttu-id="60c1a-111">**RTFSync**中发生的同步过程是消息文本，将忽略某些字符并将其他人转换的复杂循环冗余检查 (CRC)。</span><span class="sxs-lookup"><span data-stu-id="60c1a-111">The synchronization process that occurs in **RTFSync** is a sophisticated cyclic redundancy check (CRC) of the message text that ignores some characters and converts others.</span></span> <span data-ttu-id="60c1a-112">很可能由传输提供程序添加的字符将被忽略。</span><span class="sxs-lookup"><span data-stu-id="60c1a-112">Characters that most likely were added by transport providers are ignored.</span></span> <span data-ttu-id="60c1a-113">MAPI 定义用于处理 RTF 下, 表中所述的几个属性。</span><span class="sxs-lookup"><span data-stu-id="60c1a-113">MAPI defines several properties for working with RTF as described in the following table.</span></span> 
  
|<span data-ttu-id="60c1a-114">**RTF 属性**</span><span class="sxs-lookup"><span data-stu-id="60c1a-114">**RTF property**</span></span>|<span data-ttu-id="60c1a-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="60c1a-115">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60c1a-116">**PR_RTF_SYNC_BODY_TAG**([PidTagRtfSyncBodyTag](pidtagrtfsyncbodytag-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c1a-116">**PR_RTF_SYNC_BODY_TAG** ([PidTagRtfSyncBodyTag](pidtagrtfsyncbodytag-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="60c1a-117">指示实际消息文本的开头。</span><span class="sxs-lookup"><span data-stu-id="60c1a-117">Indicates the beginning of the real message text.</span></span>  <br/> |
|<span data-ttu-id="60c1a-118">**PR_RTF_SYNC_BODY_CRC**([PidTagRtfSyncBodyCrc](pidtagrtfsyncbodycrc-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c1a-118">**PR_RTF_SYNC_BODY_CRC** ([PidTagRtfSyncBodyCrc](pidtagrtfsyncbodycrc-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="60c1a-119">包含消息文本的循环冗余检查的结果。</span><span class="sxs-lookup"><span data-stu-id="60c1a-119">Contains the result of the cyclic redundancy check of the message text.</span></span>  <br/> |
|<span data-ttu-id="60c1a-120">**PR_RTF_SYNC_BODY_COUNT**([PidTagRtfSyncBodyCount](pidtagrtfsyncbodycount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c1a-120">**PR_RTF_SYNC_BODY_COUNT** ([PidTagRtfSyncBodyCount](pidtagrtfsyncbodycount-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="60c1a-121">包含**PR_RTF_SYNC_BODY_CRC**中的字符数。</span><span class="sxs-lookup"><span data-stu-id="60c1a-121">Contains the number of characters in **PR_RTF_SYNC_BODY_CRC**.</span></span>  <br/> |
|<span data-ttu-id="60c1a-122">**PR_RTF_IN_SYNC**([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c1a-122">**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="60c1a-123">设置为 true 时，邮件已同步文本和格式。</span><span class="sxs-lookup"><span data-stu-id="60c1a-123">Set to TRUE when the message text and formatting have been synchronized.</span></span>  <br/> |
|<span data-ttu-id="60c1a-124">**PR_RTF_SYNC_PREFIX_COUNT**([PidTagRtfSyncPrefixCount](pidtagrtfsyncprefixcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c1a-124">**PR_RTF_SYNC_PREFIX_COUNT** ([PidTagRtfSyncPrefixCount](pidtagrtfsyncprefixcount-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="60c1a-125">包含 nonwhitespace 字符数的低于消息文本。</span><span class="sxs-lookup"><span data-stu-id="60c1a-125">Contains the number of nonwhitespace characters that preceed the message text.</span></span>  <br/> |
|<span data-ttu-id="60c1a-126">**PR_RTF_SYNC_TRAILING_COUNT**([PidTagRtfSyncTrailingCount](pidtagrtfsynctrailingcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="60c1a-126">**PR_RTF_SYNC_TRAILING_COUNT** ([PidTagRtfSyncTrailingCount](pidtagrtfsynctrailingcount-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="60c1a-127">包含跟踪消息文本的 nonwhitespace 字符的数。</span><span class="sxs-lookup"><span data-stu-id="60c1a-127">Contains the number of nonwhitespace characters that trail the message text.</span></span>  <br/> |
   

