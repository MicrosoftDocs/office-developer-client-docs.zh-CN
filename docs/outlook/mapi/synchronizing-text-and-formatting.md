---
title: 同步文本和格式
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d7e166f0-1214-4571-b9a8-366960772a7a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 852ef988566ade8fca6551bea0d618199319d1d4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435101"
---
# <a name="synchronizing-text-and-formatting"></a><span data-ttu-id="ade39-103">同步文本和格式</span><span class="sxs-lookup"><span data-stu-id="ade39-103">Synchronizing Text and Formatting</span></span>

  
  
<span data-ttu-id="ade39-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ade39-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ade39-105">在 RTF 邮件中发送 RTF 格式 (的主要) 是使文本与格式保持同步。</span><span class="sxs-lookup"><span data-stu-id="ade39-105">The main challenge in sending Rich Text Format (RTF) messages is keeping the text synchronized with the formatting.</span></span> <span data-ttu-id="ade39-106">为了确保在邮件到达其目标位置时，它们作为预期的来源，并且文本和格式已同步，MAPI 提供了 [RTFSync](rtfsync.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="ade39-106">To ensure that when messages arrive at their destination they are as their originators intended and that the text and formatting are synchronized, MAPI provides the [RTFSync](rtfsync.md) function.</span></span> <span data-ttu-id="ade39-107">**RTFSync** 通常由 RTF 感知客户端在显示传入邮件之前调用，而 MAPI 后台程序在将邮件下载到传输提供程序时调用。</span><span class="sxs-lookup"><span data-stu-id="ade39-107">**RTFSync** is typically called by RTF-aware clients before displaying incoming messages and by the MAPI spooler when it downloads messages to a transport provider.</span></span> <span data-ttu-id="ade39-108">调用方通过向 **RTFSync** 传递一个或两个标志来指定可能存在差异的区域：</span><span class="sxs-lookup"><span data-stu-id="ade39-108">Callers specify the area of possible discrepancy by passing one or two flags to **RTFSync**:</span></span>
  
- <span data-ttu-id="ade39-109">RTF_SYNC_BODY_CHANGED指示邮件文本中的修改。</span><span class="sxs-lookup"><span data-stu-id="ade39-109">RTF_SYNC_BODY_CHANGED to indicate a modification in message text.</span></span>
    
- <span data-ttu-id="ade39-110">RTF_SYNC_RTF_CHANGED用于指示邮件格式的修改。</span><span class="sxs-lookup"><span data-stu-id="ade39-110">RTF_SYNC_RTF_CHANGED to indicate a modification in message formatting.</span></span>
    
<span data-ttu-id="ade39-111">**RTFSync** 中发生的同步过程是邮件文本的复杂的循环冗余检查 (CRC) 忽略某些字符并转换其他字符。</span><span class="sxs-lookup"><span data-stu-id="ade39-111">The synchronization process that occurs in **RTFSync** is a sophisticated cyclic redundancy check (CRC) of the message text that ignores some characters and converts others.</span></span> <span data-ttu-id="ade39-112">最有可能由传输提供程序添加的字符将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ade39-112">Characters that most likely were added by transport providers are ignored.</span></span> <span data-ttu-id="ade39-113">MAPI 定义用于 RTF 的几个属性，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="ade39-113">MAPI defines several properties for working with RTF as described in the following table.</span></span> 
  
|<span data-ttu-id="ade39-114">**RTF 属性**</span><span class="sxs-lookup"><span data-stu-id="ade39-114">**RTF property**</span></span>|<span data-ttu-id="ade39-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="ade39-115">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ade39-116">**PR_RTF_SYNC_BODY_TAG (** [PidTagRtfSyncBodyTag](pidtagrtfsyncbodytag-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="ade39-116">**PR_RTF_SYNC_BODY_TAG** ([PidTagRtfSyncBodyTag](pidtagrtfsyncbodytag-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ade39-117">指示真实邮件文本的开头。</span><span class="sxs-lookup"><span data-stu-id="ade39-117">Indicates the beginning of the real message text.</span></span>  <br/> |
|<span data-ttu-id="ade39-118">**PR_RTF_SYNC_BODY_CRC (** [PidTagRtfSyncBodyCrc](pidtagrtfsyncbodycrc-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="ade39-118">**PR_RTF_SYNC_BODY_CRC** ([PidTagRtfSyncBodyCrc](pidtagrtfsyncbodycrc-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ade39-119">包含邮件文本的循环冗余检查的结果。</span><span class="sxs-lookup"><span data-stu-id="ade39-119">Contains the result of the cyclic redundancy check of the message text.</span></span>  <br/> |
|<span data-ttu-id="ade39-120">**PR_RTF_SYNC_BODY_COUNT (** [PidTagRtfSyncBodyCount](pidtagrtfsyncbodycount-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="ade39-120">**PR_RTF_SYNC_BODY_COUNT** ([PidTagRtfSyncBodyCount](pidtagrtfsyncbodycount-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ade39-121">包含文件 中的字符 **PR_RTF_SYNC_BODY_CRC。**</span><span class="sxs-lookup"><span data-stu-id="ade39-121">Contains the number of characters in **PR_RTF_SYNC_BODY_CRC**.</span></span>  <br/> |
|<span data-ttu-id="ade39-122">**PR_RTF_IN_SYNC (** [PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="ade39-122">**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ade39-123">如果邮件文本和格式已同步，则设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="ade39-123">Set to TRUE when the message text and formatting have been synchronized.</span></span>  <br/> |
|<span data-ttu-id="ade39-124">**PR_RTF_SYNC_PREFIX_COUNT (** [PidTagRtfSyncPrefixCount](pidtagrtfsyncprefixcount-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="ade39-124">**PR_RTF_SYNC_PREFIX_COUNT** ([PidTagRtfSyncPrefixCount](pidtagrtfsyncprefixcount-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ade39-125">包含邮件文本之前的非空字符数。</span><span class="sxs-lookup"><span data-stu-id="ade39-125">Contains the number of nonwhitespace characters that preceed the message text.</span></span>  <br/> |
|<span data-ttu-id="ade39-126">**PR_RTF_SYNC_TRAILING_COUNT (** [PidTagRtfSyncTrailingCount)](pidtagrtfsynctrailingcount-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="ade39-126">**PR_RTF_SYNC_TRAILING_COUNT** ([PidTagRtfSyncTrailingCount](pidtagrtfsynctrailingcount-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="ade39-127">包含邮件文本结尾的非空字符数。</span><span class="sxs-lookup"><span data-stu-id="ade39-127">Contains the number of nonwhitespace characters that trail the message text.</span></span>  <br/> |
   

