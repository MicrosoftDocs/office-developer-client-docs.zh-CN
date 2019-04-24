---
title: 在传出邮件中支持格式化的文本客户端责任
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7238b1a9-01ed-46a0-a625-26763323317d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 01d5ae3fd06d570e15336fad9538f01e586cd0f3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327403"
---
# <a name="supporting-formatted-text-in-outgoing-messages-client-responsibilities"></a><span data-ttu-id="00b29-103">在待发邮件中支持格式化文本: 客户端责任</span><span class="sxs-lookup"><span data-stu-id="00b29-103">Supporting Formatted Text in Outgoing Messages: Client Responsibilities</span></span>

  
  
<span data-ttu-id="00b29-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="00b29-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="00b29-105">客户端应用程序设置**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性、 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性或传出邮件的**PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="00b29-105">Client applications set the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property, the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property, or the **PR_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) property for an outgoing message.</span></span> <span data-ttu-id="00b29-106">仅支持纯文本的客户端仅设置**PR_BODY**属性。</span><span class="sxs-lookup"><span data-stu-id="00b29-106">Clients that support only plain text set only the **PR_BODY** property.</span></span> <span data-ttu-id="00b29-107">rtf 格式 (rtf) 感知客户端可以设置**PR_BODY**和**PR_RTF_COMPRESSED**属性, 也可以仅设置**PR_RTF_COMPRESSED**, 具体取决于所使用的邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="00b29-107">Rich Text Format (RTF)-aware clients might set both **PR_BODY** and **PR_RTF_COMPRESSED** properties, or only **PR_RTF_COMPRESSED**, depending on the message store provider being used.</span></span> <span data-ttu-id="00b29-108">HTML 感知客户端设置**PR_HTML**属性。</span><span class="sxs-lookup"><span data-stu-id="00b29-108">HTML-aware clients set the **PR_HTML** property.</span></span> 
  
<span data-ttu-id="00b29-109">客户端必须检查其邮件存储的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性以确定存储是否支持 RTF, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="00b29-109">It is important for a client to check its message store's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property to determine whether the store supports RTF.</span></span> <span data-ttu-id="00b29-110">如果邮件存储区不能识别 rtf, 则 rtf 感知客户端会为每个传出邮件设置**PR_BODY**和**PR_RTF_COMPRESSED**属性。</span><span class="sxs-lookup"><span data-stu-id="00b29-110">If the message store is not RTF-aware, an RTF-aware client sets both the **PR_BODY** and **PR_RTF_COMPRESSED** properties for each outgoing message.</span></span> 
  
<span data-ttu-id="00b29-111">如果邮件存储区是 RTF 的, 则只需设置**PR_RTF_COMPRESSED**属性。</span><span class="sxs-lookup"><span data-stu-id="00b29-111">If the message store is RTF-aware, only the **PR_RTF_COMPRESSED** property needs to be set.</span></span> 
  
 <span data-ttu-id="00b29-112">**设置 PR_RTF_COMPRESSED 并确保同步过程在必要时进行; RTF 感知客户端**</span><span class="sxs-lookup"><span data-stu-id="00b29-112">**To set PR_RTF_COMPRESSED and ensure that the synchronization process occurs as necessary, RTF-aware clients**</span></span>
  
1. <span data-ttu-id="00b29-113">调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以打开**PR_RTF_COMPRESSED**属性, 同时设置 MAPI_CREATE 和 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="00b29-113">Call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_RTF_COMPRESSED** property, setting both the MAPI_CREATE and MAPI_MODIFY flags.</span></span> <span data-ttu-id="00b29-114">MAPI_CREATE 确保任何新数据将替换任何旧的数据和 MAPI_MODIFY, 使您能够进行这些替换。</span><span class="sxs-lookup"><span data-stu-id="00b29-114">MAPI_CREATE ensures that any new data replaces any old data and MAPI_MODIFY enables you to make those replacements.</span></span> 
    
2. <span data-ttu-id="00b29-115">调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数, 如果邮件存储区在其**PR_STORE_SUPPORT_MASK**属性中设置了 STORE_UNCOMPRESSED_RTF 位, 则传递 STORE_UNCOMPRESSED_RTF, 以获取 PR_RTF_COMPRESSED 的未压缩版本。 \*\*\*\* 从**OpenProperty**返回的流。</span><span class="sxs-lookup"><span data-stu-id="00b29-115">Call the [WrapCompressedRTFStream](wrapcompressedrtfstream.md) function, passing STORE_UNCOMPRESSED_RTF if the message store sets the STORE_UNCOMPRESSED_RTF bit in its **PR_STORE_SUPPORT_MASK** property, to get an uncompressed version of the **PR_RTF_COMPRESSED** stream returned from **OpenProperty**.</span></span>
    
3. <span data-ttu-id="00b29-116">将邮件文本数据写入从**WrapCompressedRTFStream**返回的未压缩流。</span><span class="sxs-lookup"><span data-stu-id="00b29-116">Write the message text data to the uncompressed stream returned from **WrapCompressedRTFStream**.</span></span>
    
4. <span data-ttu-id="00b29-117">提交并释放未压缩和压缩的流。</span><span class="sxs-lookup"><span data-stu-id="00b29-117">Commit and release both the uncompressed and compressed streams.</span></span>
    
<span data-ttu-id="00b29-118">在这种情况下, 如果邮件存储区提供程序支持 RTF, 则您已完成所有必需的操作。</span><span class="sxs-lookup"><span data-stu-id="00b29-118">At this point, if the message store provider supports RTF, you have done all that is required.</span></span> <span data-ttu-id="00b29-119">您可以根据邮件存储提供程序来处理同步过程和创建**PR_BODY**属性 (如有必要)。</span><span class="sxs-lookup"><span data-stu-id="00b29-119">You can depend on the message store provider to handle the synchronization process and the creation of the **PR_BODY** property, if necessary.</span></span> <span data-ttu-id="00b29-120">但是, 如果邮件存储区提供程序不支持 RTF, 则必须调用[RTFSync](rtfsync.md)函数以将文本与格式设置同步, 设置 RTF_SYNC_RTF_CHANGED 标志。</span><span class="sxs-lookup"><span data-stu-id="00b29-120">However, if the message store provider does not support RTF, you must call the [RTFSync](rtfsync.md) function to synchronize the text with the formatting, setting the RTF_SYNC_RTF_CHANGED flag.</span></span> 
  

