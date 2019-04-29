---
title: 创建邮件文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 70d1fb24-91a9-4043-8c9d-be1523012e6b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5b4a4107d6326a61f50a4023ebc2538f699224b5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428002"
---
# <a name="creating-message-text"></a><span data-ttu-id="61104-103">创建邮件文本</span><span class="sxs-lookup"><span data-stu-id="61104-103">Creating message text</span></span>

<span data-ttu-id="61104-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="61104-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="61104-105">虽然某些邮件是由收件人列表和主题行组成, 但大多数邮件的内容 (尤其是 IPM) 除外。注释邮件包括文本。</span><span class="sxs-lookup"><span data-stu-id="61104-105">Although some messages are made up of nothing more than a recipient list and a subject line, the content of most messages, specifically IPM.Note messages, includes text.</span></span> <span data-ttu-id="61104-106">邮件文本可以是纯文本或格式的, 并存储在以下三个属性中: **PR\_BODY** ([PidTagBody](pidtagbody-canonical-property.md))、 **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="61104-106">Message text can be plain or formatted and is stored in three properties: **PR\_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)), and **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)).</span></span> 

<span data-ttu-id="61104-107">如果您的客户端是纯文本, 请**设置\_PR 正文**。</span><span class="sxs-lookup"><span data-stu-id="61104-107">If your client is plain text-based, set **PR\_BODY**.</span></span> <span data-ttu-id="61104-108">如果您支持 rtf 格式的格式化文本, 请仅设置 " **PR_RTF_COMPRESSED** " 或 " **PR_RTF_COMPRESSED** " 和 " **PR\_正文**", 具体取决于所使用的邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="61104-108">If you support formatted text in the Rich Text Format (RTF), set either **PR_RTF_COMPRESSED** only or both **PR_RTF_COMPRESSED** and **PR\_BODY**, depending on the message store provider that you are using.</span></span> <span data-ttu-id="61104-109">当 rtf 感知客户端使用的是 rtf 感知邮件存储时, 它只会设置**PR_RTF_COMPRESSED** 。</span><span class="sxs-lookup"><span data-stu-id="61104-109">When an RTF-aware client is using an RTF-aware message store, it sets **PR_RTF_COMPRESSED** only.</span></span> <span data-ttu-id="61104-110">当 RTF 感知客户端使用非 RTF 感知邮件存储区时, 它会同时设置这两个属性。</span><span class="sxs-lookup"><span data-stu-id="61104-110">When an RTF-aware client is using a non-RTF-aware message store, it sets both properties.</span></span> <span data-ttu-id="61104-111">如果您的客户端支持 HTML, 请设置**PR_HTML**属性。</span><span class="sxs-lookup"><span data-stu-id="61104-111">If your client supports HTML, set the **PR_HTML** property.</span></span> 
  
## <a name="determine-whether-your-message-store-supports-rich-text-format"></a><span data-ttu-id="61104-112">确定您的邮件存储区是否支持 rtf 格式</span><span class="sxs-lookup"><span data-stu-id="61104-112">Determine whether your message store supports Rich Text Format</span></span>
  
1. <span data-ttu-id="61104-113">调用邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="61104-113">Call the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property.</span></span>
    
2. <span data-ttu-id="61104-114">检查 STORE_RTF_OK 位。</span><span class="sxs-lookup"><span data-stu-id="61104-114">Check for the STORE_RTF_OK bit.</span></span> <span data-ttu-id="61104-115">如果设置了 STORE_RTF_OK, 则邮件存储提供程序支持 RTF 文本。</span><span class="sxs-lookup"><span data-stu-id="61104-115">If STORE_RTF_OK is set, the message store provider supports RTF text.</span></span> <span data-ttu-id="61104-116">如果未设置, 则邮件存储提供程序仅支持纯文本。</span><span class="sxs-lookup"><span data-stu-id="61104-116">If it is not set, the message store provider supports plain text only.</span></span>
    
## <a name="determine-whether-your-message-store-supports-html"></a><span data-ttu-id="61104-117">确定您的邮件存储区是否支持 HTML</span><span class="sxs-lookup"><span data-stu-id="61104-117">Determine whether your message store supports HTML</span></span>
  
1. <span data-ttu-id="61104-118">调用邮件存储区的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_STORE_SUPPORT_MASK**属性。</span><span class="sxs-lookup"><span data-stu-id="61104-118">Call the message store's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_STORE_SUPPORT_MASK** property.</span></span> 
    
2. <span data-ttu-id="61104-119">检查 STORE_HTML_OK 位。</span><span class="sxs-lookup"><span data-stu-id="61104-119">Check for the STORE_HTML_OK bit.</span></span> <span data-ttu-id="61104-120">如果设置了 STORE_HTML_OK, 则邮件存储提供程序支持 HTML 文本。</span><span class="sxs-lookup"><span data-stu-id="61104-120">If STORE_HTML_OK is set, the message store provider supports HTML text.</span></span> 
    
## <a name="set-prrtfcompressed"></a><span data-ttu-id="61104-121">设置 PR\_RTF_COMPRESSED</span><span class="sxs-lookup"><span data-stu-id="61104-121">Set PR\_RTF_COMPRESSED</span></span>
  
1. <span data-ttu-id="61104-122">调用邮件的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以打开**PR_RTF_COMPRESSED**属性, 指定 IID_IStream 作为接口标识符并设置 MAPI_CREATE 标志。</span><span class="sxs-lookup"><span data-stu-id="61104-122">Call the message's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_RTF_COMPRESSED** property, specifying IID_IStream as the interface identifier and setting the MAPI_CREATE flag.</span></span> 
    
2. <span data-ttu-id="61104-123">如果在邮件存储区的**PR_STORE_SUPPORT_MASK**属性中设置了 STORE_UNCOMPRESSED_RTF 位, 请调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数, 并传递 STORE_UNCOMPRESSED_RTF 标志。</span><span class="sxs-lookup"><span data-stu-id="61104-123">Call the [WrapCompressedRTFStream](wrapcompressedrtfstream.md) function, passing the STORE_UNCOMPRESSED_RTF flag if the STORE_UNCOMPRESSED_RTF bit is set in the message store's **PR_STORE_SUPPORT_MASK** property.</span></span> 
    
3. <span data-ttu-id="61104-124">通过调用其 \* \* IUnknown:: Release \* \* 方法释放原始流。</span><span class="sxs-lookup"><span data-stu-id="61104-124">Release the original stream by calling its \*\* IUnknown::Release \*\* method.</span></span> 
    
4. <span data-ttu-id="61104-125">调用 \* \* IStream:: Write \* \* 或**IStream:: CopyTo**将消息文本写入从**WrapCompressedRTFStream**返回的流。</span><span class="sxs-lookup"><span data-stu-id="61104-125">Call either \*\* IStream::Write \*\* or **IStream::CopyTo** to write the message text to the stream returned from **WrapCompressedRTFStream**.</span></span>
    
5. <span data-ttu-id="61104-126">调用**OpenProperty**方法返回的 stream 上的**Commit**和**Release**方法。</span><span class="sxs-lookup"><span data-stu-id="61104-126">Call the **Commit** and **Release** methods on the stream returned from the **OpenProperty** method.</span></span> 
    
<span data-ttu-id="61104-127">在这种情况下, 如果邮件存储区提供程序支持 RTF, 则您已完成所有必需的操作。</span><span class="sxs-lookup"><span data-stu-id="61104-127">At this point, if the message store provider supports RTF, you have done all that is required.</span></span> <span data-ttu-id="61104-128">您可以依赖邮件存储提供程序来处理邮件内容和格式的同步, 并在必要时创建 " **PR\_正文**" 属性。</span><span class="sxs-lookup"><span data-stu-id="61104-128">You can depend on the message store provider to handle synchronizing the message content and formatting and to create the **PR\_BODY** property if necessary.</span></span> <span data-ttu-id="61104-129">RTF 感知邮件存储区调用[RTFSync](rtfsync.md)以处理同步。</span><span class="sxs-lookup"><span data-stu-id="61104-129">RTF-aware message stores call [RTFSync](rtfsync.md) to handle the synchronization.</span></span> <span data-ttu-id="61104-130">如果 RTF\_SYNC_BODY_CHANGED 标志设置为 TRUE, 则提供程序将重新计算**PR_BODY**属性。</span><span class="sxs-lookup"><span data-stu-id="61104-130">If the RTF\_SYNC_BODY_CHANGED flag is set to TRUE, the provider will recompute the **PR_BODY** property.</span></span> 
  
<span data-ttu-id="61104-131">如果您的邮件存储区提供程序不支持 rtf, 还必须通过设置**PR_BODY**属性来添加非 RTF 邮件内容。</span><span class="sxs-lookup"><span data-stu-id="61104-131">If your message store provider does not support RTF, you must also add non-RTF message content by setting the **PR_BODY** property.</span></span> 
  
## <a name="set-prhtml"></a><span data-ttu-id="61104-132">设置 PR_HTML</span><span class="sxs-lookup"><span data-stu-id="61104-132">Set PR_HTML</span></span>
  
1. <span data-ttu-id="61104-133">调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以使用**IStream**接口打开**PR_HTML**属性。</span><span class="sxs-lookup"><span data-stu-id="61104-133">Call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_HTML** property with the **IStream** interface.</span></span> 
    
2. <span data-ttu-id="61104-134">调用**IStream:: write** , 用于将消息文本数据写入从**OpenProperty**返回的流。</span><span class="sxs-lookup"><span data-stu-id="61104-134">Call **IStream::Write** to write the message text data to the stream returned from **OpenProperty**.</span></span> 
    
3. <span data-ttu-id="61104-135">调用**IStream:: commit**和**IUnknown:: Release** on stream 以提交更改并释放其内存。</span><span class="sxs-lookup"><span data-stu-id="61104-135">Call **IStream::Commit** and **IUnknown::Release** on the stream to commit the changes and free its memory.</span></span> 
    
## <a name="set-prbody"></a><span data-ttu-id="61104-136">设置 PR_BODY</span><span class="sxs-lookup"><span data-stu-id="61104-136">Set PR_BODY</span></span>
  
1. <span data-ttu-id="61104-137">调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以使用**IStream**接口打开**PR_BODY**属性。</span><span class="sxs-lookup"><span data-stu-id="61104-137">Call the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_BODY** property with the **IStream** interface.</span></span> 
    
2. <span data-ttu-id="61104-138">调用**IStream:: write** , 用于将消息文本数据写入从**OpenProperty**返回的流。</span><span class="sxs-lookup"><span data-stu-id="61104-138">Call **IStream::Write** to write the message text data to the stream returned from **OpenProperty**.</span></span> 
    
3. <span data-ttu-id="61104-139">调用[RTFSync](rtfsync.md)函数以将文本与格式设置同步。</span><span class="sxs-lookup"><span data-stu-id="61104-139">Call the [RTFSync](rtfsync.md) function to synchronize the text with the formatting.</span></span> <span data-ttu-id="61104-140">由于这是一封新邮件, 因此应设置 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED 标志, 以指示邮件文本的 RTF 和纯文本版本已更改。</span><span class="sxs-lookup"><span data-stu-id="61104-140">Because this is a new message, set both the RTF_SYNC_RTF_CHANGED and RTF_SYNC_BODY_CHANGED flags to indicate that both the RTF and plain text version of the message text has changed.</span></span> <span data-ttu-id="61104-141">**RTFSync**将设置邮件存储提供程序所需的多个相关属性, 如**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)), 并将其写入邮件。</span><span class="sxs-lookup"><span data-stu-id="61104-141">**RTFSync** will set several related properties that the message store provider requires, such as **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)), and write them to the message.</span></span>
    
4. <span data-ttu-id="61104-142">调用**IStream:: commit**和**IUnknown:: Release** on stream 以提交更改并释放其内存。</span><span class="sxs-lookup"><span data-stu-id="61104-142">Call **IStream::Commit** and **IUnknown::Release** on the stream to commit the changes and free its memory.</span></span> 
    

