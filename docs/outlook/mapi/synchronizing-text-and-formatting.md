---
title: 同步文本和格式设置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d7e166f0-1214-4571-b9a8-366960772a7a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 852ef988566ade8fca6551bea0d618199319d1d4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346597"
---
# <a name="synchronizing-text-and-formatting"></a><span data-ttu-id="a9fd9-103">同步文本和格式设置</span><span class="sxs-lookup"><span data-stu-id="a9fd9-103">Synchronizing Text and Formatting</span></span>

  
  
<span data-ttu-id="a9fd9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a9fd9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a9fd9-105">发送 rtf 格式 (rtf) 邮件的主要挑战是使文本与格式保持同步。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-105">The main challenge in sending Rich Text Format (RTF) messages is keeping the text synchronized with the formatting.</span></span> <span data-ttu-id="a9fd9-106">若要确保当邮件到达其目标时, 它们是其原始发件人, 并且文本和格式设置已同步, MAPI 提供了[RTFSync](rtfsync.md)函数。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-106">To ensure that when messages arrive at their destination they are as their originators intended and that the text and formatting are synchronized, MAPI provides the [RTFSync](rtfsync.md) function.</span></span> <span data-ttu-id="a9fd9-107">在显示传入的邮件和 MAPI 后台处理程序将邮件下载到传输提供程序中之前, **RTFSync**通常由 RTF 感知客户端调用。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-107">**RTFSync** is typically called by RTF-aware clients before displaying incoming messages and by the MAPI spooler when it downloads messages to a transport provider.</span></span> <span data-ttu-id="a9fd9-108">通过将一个或两个标志传递给**RTFSync**, 调用方可以指定可能的差异区域:</span><span class="sxs-lookup"><span data-stu-id="a9fd9-108">Callers specify the area of possible discrepancy by passing one or two flags to **RTFSync**:</span></span>
  
- <span data-ttu-id="a9fd9-109">RTF_SYNC_BODY_CHANGED, 以指示邮件文本中的修改。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-109">RTF_SYNC_BODY_CHANGED to indicate a modification in message text.</span></span>
    
- <span data-ttu-id="a9fd9-110">RTF_SYNC_RTF_CHANGED 以指示邮件格式中的修改。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-110">RTF_SYNC_RTF_CHANGED to indicate a modification in message formatting.</span></span>
    
<span data-ttu-id="a9fd9-111">**RTFSync**中发生的同步过程是邮件文本的复杂循环冗余检查 (CRC), 它会忽略某些字符并转换其他字符。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-111">The synchronization process that occurs in **RTFSync** is a sophisticated cyclic redundancy check (CRC) of the message text that ignores some characters and converts others.</span></span> <span data-ttu-id="a9fd9-112">由传输提供程序添加的最可能的字符将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-112">Characters that most likely were added by transport providers are ignored.</span></span> <span data-ttu-id="a9fd9-113">MAPI 定义了几个用于处理 RTF 的属性, 如下表所述。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-113">MAPI defines several properties for working with RTF as described in the following table.</span></span> 
  
|<span data-ttu-id="a9fd9-114">**RTF 属性**</span><span class="sxs-lookup"><span data-stu-id="a9fd9-114">**RTF property**</span></span>|<span data-ttu-id="a9fd9-115">**Description**</span><span class="sxs-lookup"><span data-stu-id="a9fd9-115">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9fd9-116">**PR_RTF_SYNC_BODY_TAG**([PidTagRtfSyncBodyTag](pidtagrtfsyncbodytag-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a9fd9-116">**PR_RTF_SYNC_BODY_TAG** ([PidTagRtfSyncBodyTag](pidtagrtfsyncbodytag-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="a9fd9-117">指示实际邮件文本的开头。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-117">Indicates the beginning of the real message text.</span></span>  <br/> |
|<span data-ttu-id="a9fd9-118">**PR_RTF_SYNC_BODY_CRC**([PidTagRtfSyncBodyCrc](pidtagrtfsyncbodycrc-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a9fd9-118">**PR_RTF_SYNC_BODY_CRC** ([PidTagRtfSyncBodyCrc](pidtagrtfsyncbodycrc-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="a9fd9-119">包含邮件文本的循环冗余检查的结果。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-119">Contains the result of the cyclic redundancy check of the message text.</span></span>  <br/> |
|<span data-ttu-id="a9fd9-120">**PR_RTF_SYNC_BODY_COUNT**([PidTagRtfSyncBodyCount](pidtagrtfsyncbodycount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a9fd9-120">**PR_RTF_SYNC_BODY_COUNT** ([PidTagRtfSyncBodyCount](pidtagrtfsyncbodycount-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="a9fd9-121">包含**PR_RTF_SYNC_BODY_CRC**中的字符数。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-121">Contains the number of characters in **PR_RTF_SYNC_BODY_CRC**.</span></span>  <br/> |
|<span data-ttu-id="a9fd9-122">**PR_RTF_IN_SYNC**([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a9fd9-122">**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="a9fd9-123">如果邮件文本和格式已同步, 则设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-123">Set to TRUE when the message text and formatting have been synchronized.</span></span>  <br/> |
|<span data-ttu-id="a9fd9-124">**PR_RTF_SYNC_PREFIX_COUNT**([PidTagRtfSyncPrefixCount](pidtagrtfsyncprefixcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a9fd9-124">**PR_RTF_SYNC_PREFIX_COUNT** ([PidTagRtfSyncPrefixCount](pidtagrtfsyncprefixcount-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="a9fd9-125">包含 preceed 邮件文本的 nonwhitespace 字符的数目。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-125">Contains the number of nonwhitespace characters that preceed the message text.</span></span>  <br/> |
|<span data-ttu-id="a9fd9-126">**PR_RTF_SYNC_TRAILING_COUNT**([PidTagRtfSyncTrailingCount](pidtagrtfsynctrailingcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a9fd9-126">**PR_RTF_SYNC_TRAILING_COUNT** ([PidTagRtfSyncTrailingCount](pidtagrtfsynctrailingcount-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="a9fd9-127">包含跟踪邮件文本的 nonwhitespace 字符的数量。</span><span class="sxs-lookup"><span data-stu-id="a9fd9-127">Contains the number of nonwhitespace characters that trail the message text.</span></span>  <br/> |
   

