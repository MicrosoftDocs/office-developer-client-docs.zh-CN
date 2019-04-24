---
title: 在 RTF 文本中呈现附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 26372539-e9fe-464d-95c7-90b58c20b98f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b2a1a23f073d05e85c8203826e3407c5ae193f19
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280357"
---
# <a name="rendering-an-attachment-in-rtf-text"></a><span data-ttu-id="3ccf7-103">在 RTF 文本中呈现附件</span><span class="sxs-lookup"><span data-stu-id="3ccf7-103">Rendering an Attachment in RTF Text</span></span>

  
  
<span data-ttu-id="3ccf7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3ccf7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3ccf7-105">rtf 格式 (rtf) 感知客户端可以通过在邮件的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中查找以下转义序列来检索 RTF 邮件文本中的呈现位置信息:</span><span class="sxs-lookup"><span data-stu-id="3ccf7-105">Rich Text Format (RTF)-aware clients can retrieve rendering position information from RTF message text by looking for the following escape sequence in the message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property:</span></span>
  
 `\objattph`
  
 <span data-ttu-id="3ccf7-106">**在格式化文本中查找呈现信息**</span><span class="sxs-lookup"><span data-stu-id="3ccf7-106">**To locate rendering information in formatted text**</span></span>
  
1. <span data-ttu-id="3ccf7-107">调用**IMessage:: GetAttachmentTable**以访问邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-107">Call **IMessage::GetAttachmentTable** to access the message's attachment table.</span></span> <span data-ttu-id="3ccf7-108">有关详细信息, 请参阅[IMessage:: GetAttachmentTable](imessage-getattachmenttable.md)。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-108">For more information, see [IMessage::GetAttachmentTable](imessage-getattachmenttable.md).</span></span>
    
2. <span data-ttu-id="3ccf7-109">生成将表限制为**PR_RENDERING_POSITION**不等于-1 的行的属性限制。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-109">Build a property restriction that limits the table to rows that have **PR_RENDERING_POSITION** not equal to -1.</span></span> <span data-ttu-id="3ccf7-110">有关详细信息, 请参阅**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-110">For more information, see **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="3ccf7-111">调用**IMAPITable:: Restrict**以强制实施限制。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-111">Call **IMAPITable::Restrict** to enforce the restriction.</span></span> <span data-ttu-id="3ccf7-112">有关详细信息, 请参阅[IMAPITable:: Restrict](imapitable-restrict.md)。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-112">For more information, see [IMAPITable::Restrict](imapitable-restrict.md).</span></span>
    
4. <span data-ttu-id="3ccf7-113">调用**IMAPITable:: SortTable**对附件进行排序。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-113">Call **IMAPITable::SortTable** to sort the attachments.</span></span> <span data-ttu-id="3ccf7-114">有关详细信息, 请参阅[IMAPITable:: SortTable](imapitable-sorttable.md)。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-114">For more information, see [IMAPITable::SortTable](imapitable-sorttable.md).</span></span>
    
5. <span data-ttu-id="3ccf7-115">调用**IMAPITable:: QueryRows**以检索相应的行。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-115">Call **IMAPITable::QueryRows** to retrieve the appropriate rows.</span></span> <span data-ttu-id="3ccf7-116">有关详细信息, 请参阅[IMAPITable:: QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-116">For more information, see [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span>
    
6. <span data-ttu-id="3ccf7-117">调用邮件的**IMAPIProp:: OpenProperty**方法, 以使用**IStream**接口检索**PR_RTF_COMPRESSED** 。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-117">Call the message's **IMAPIProp::OpenProperty** method to retrieve **PR_RTF_COMPRESSED** with the **IStream** interface.</span></span> <span data-ttu-id="3ccf7-118">有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-118">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**.</span></span>
    
7. <span data-ttu-id="3ccf7-119">扫描流, 查找呈现占位符`\objattph`。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-119">Scan the stream, looking for the rendering placeholder,  `\objattph`.</span></span> <span data-ttu-id="3ccf7-120">此占位符后面的字符是排序表中下一个附件的位置。</span><span class="sxs-lookup"><span data-stu-id="3ccf7-120">The character following this placeholder is the place for the next attachment in the sorted table.</span></span>
    

