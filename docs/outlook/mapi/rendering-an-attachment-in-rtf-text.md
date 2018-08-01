---
title: 以 RTF 文本呈现附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 26372539-e9fe-464d-95c7-90b58c20b98f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cf22e360a0319a662c9b7dd31856dbb6eccec02a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778611"
---
# <a name="rendering-an-attachment-in-rtf-text"></a><span data-ttu-id="67399-103">以 RTF 文本呈现附件</span><span class="sxs-lookup"><span data-stu-id="67399-103">Rendering an Attachment in RTF Text</span></span>

  
  
<span data-ttu-id="67399-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="67399-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="67399-105">Rtf 格式 (RTF)-感知客户端可以通过查看消息的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中下面的转义序列从 RTF 邮件文本检索呈现位置信息：</span><span class="sxs-lookup"><span data-stu-id="67399-105">Rich Text Format (RTF)-aware clients can retrieve rendering position information from RTF message text by looking for the following escape sequence in the message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property:</span></span>
  
 `\objattph`
  
 <span data-ttu-id="67399-106">**若要找到格式化文本呈现信息**</span><span class="sxs-lookup"><span data-stu-id="67399-106">**To locate rendering information in formatted text**</span></span>
  
1. <span data-ttu-id="67399-107">调用**IMessage::GetAttachmentTable**访问邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="67399-107">Call **IMessage::GetAttachmentTable** to access the message's attachment table.</span></span> <span data-ttu-id="67399-108">有关详细信息，请参阅[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)。</span><span class="sxs-lookup"><span data-stu-id="67399-108">For more information, see [IMessage::GetAttachmentTable](imessage-getattachmenttable.md).</span></span>
    
2. <span data-ttu-id="67399-109">构建限制表格行具有**PR_RENDERING_POSITION**不等于-1 的属性限制。</span><span class="sxs-lookup"><span data-stu-id="67399-109">Build a property restriction that limits the table to rows that have **PR_RENDERING_POSITION** not equal to -1.</span></span> <span data-ttu-id="67399-110">有关详细信息，请参阅**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="67399-110">For more information, see **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="67399-111">调用**IMAPITable::Restrict**强制实施的限制。</span><span class="sxs-lookup"><span data-stu-id="67399-111">Call **IMAPITable::Restrict** to enforce the restriction.</span></span> <span data-ttu-id="67399-112">有关详细信息，请参阅[IMAPITable::Restrict](imapitable-restrict.md)。</span><span class="sxs-lookup"><span data-stu-id="67399-112">For more information, see [IMAPITable::Restrict](imapitable-restrict.md).</span></span>
    
4. <span data-ttu-id="67399-113">调用**IMAPITable::SortTable**排序附件。</span><span class="sxs-lookup"><span data-stu-id="67399-113">Call **IMAPITable::SortTable** to sort the attachments.</span></span> <span data-ttu-id="67399-114">有关详细信息，请参阅[IMAPITable::SortTable](imapitable-sorttable.md)。</span><span class="sxs-lookup"><span data-stu-id="67399-114">For more information, see [IMAPITable::SortTable](imapitable-sorttable.md).</span></span>
    
5. <span data-ttu-id="67399-115">调用**IMAPITable::QueryRows**检索合适的行。</span><span class="sxs-lookup"><span data-stu-id="67399-115">Call **IMAPITable::QueryRows** to retrieve the appropriate rows.</span></span> <span data-ttu-id="67399-116">有关详细信息，请参阅[IMAPITable::QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="67399-116">For more information, see [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span>
    
6. <span data-ttu-id="67399-117">调用消息的**IMAPIProp::OpenProperty**方法，以检索与**IStream**接口**PR_RTF_COMPRESSED** 。</span><span class="sxs-lookup"><span data-stu-id="67399-117">Call the message's **IMAPIProp::OpenProperty** method to retrieve **PR_RTF_COMPRESSED** with the **IStream** interface.</span></span> <span data-ttu-id="67399-118">有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)和**PR_RTF_COMPRESSED**。</span><span class="sxs-lookup"><span data-stu-id="67399-118">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**.</span></span>
    
7. <span data-ttu-id="67399-119">扫描流，呈现占位符中，查找`\objattph`。</span><span class="sxs-lookup"><span data-stu-id="67399-119">Scan the stream, looking for the rendering placeholder,  `\objattph`.</span></span> <span data-ttu-id="67399-120">关注此占位符的字符是一个已排序的表中的下一个附件。</span><span class="sxs-lookup"><span data-stu-id="67399-120">The character following this placeholder is the place for the next attachment in the sorted table.</span></span>
    

