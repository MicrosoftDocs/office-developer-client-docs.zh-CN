---
title: 附加的文件和邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b2f2fb72-23ae-4e0b-a8a1-3b78a1862acb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c4dbe1a761a753bef77168aec8d2674a1b2b100e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436837"
---
# <a name="attached-files-and-messages"></a><span data-ttu-id="22d3a-103">附加的文件和邮件</span><span class="sxs-lookup"><span data-stu-id="22d3a-103">Attached Files and Messages</span></span>

  
  
<span data-ttu-id="22d3a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="22d3a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="22d3a-105">如果在对邮件内容进行编码时使用了带有 TNEF 的 MIME, 则所有附件属性和内容都在 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="22d3a-105">If MIME with TNEF is used while encoding message content,all attachment properties and content are in the TNEF stream.</span></span> <span data-ttu-id="22d3a-106">TNEF 本身是一个名为 winmail.dat 的二进制附加文件, 编码为对不带 TNEF 的 MIME 所做的编码。</span><span class="sxs-lookup"><span data-stu-id="22d3a-106">The TNEF itself is a single, binary attached file named Winmail.dat, encoded as described for MIME without TNEF.</span></span> 
  
<span data-ttu-id="22d3a-107">如果在没有 TNEF 的情况下使用 MIME, 附加的文件将作为 MIME 邮件内容部分发送。</span><span class="sxs-lookup"><span data-stu-id="22d3a-107">If MIME is used without TNEF, attached files are sent as MIME message content parts.</span></span> <span data-ttu-id="22d3a-108">filename 放置在附件的*内容类型*标头的*name*参数中。</span><span class="sxs-lookup"><span data-stu-id="22d3a-108">The filename is placed in the  *name*  parameter to the  *Content-type*  header for the attachment.</span></span> <span data-ttu-id="22d3a-109">将附件的字符集放在*内容类型*的*字符集*参数中;通过扫描整个附件内容来确定它和内容传送编码。</span><span class="sxs-lookup"><span data-stu-id="22d3a-109">The character set for the attachment is placed in the  *charset*  parameter to the  *Content-type*  ; it and the content-transfer-encoding are determined by scanning the entire attachment content.</span></span> <span data-ttu-id="22d3a-110">特殊处理 URL 附件:</span><span class="sxs-lookup"><span data-stu-id="22d3a-110">URL attachments are treated specially:</span></span> 
  
- <span data-ttu-id="22d3a-111">如果附件是 URL (扩展名为的附加文件)。URL), 并且在其中定义的访问模式是匿名 FTP, 它被编码为外部邮件, 并且将文件的内容 (URL) 复制到外部邮件的标头中。</span><span class="sxs-lookup"><span data-stu-id="22d3a-111">If the attachment is a URL (an attached file with extension .URL), and the access mode defined in it is anonymous FTP, it is encoded as an external message, and the content of the file (the URL) is copied into the header of the external message.</span></span> <span data-ttu-id="22d3a-112">*Content-type: message/external-body; 访问类型 = anon-ftp* (内容传输编码: 假定为7bit。)</span><span class="sxs-lookup"><span data-stu-id="22d3a-112">*Content-type: message/external-body; access-type=anon-ftp*  (Content-Transfer-Encoding: 7bit is assumed.)</span></span> 
    
- <span data-ttu-id="22d3a-113">如果仅找到7位字符, 并且没有任何行的长度超过140个字符, 则附件为 ASCII 文本。</span><span class="sxs-lookup"><span data-stu-id="22d3a-113">If only 7-bit characters are found and no line exceeds 140 characters in length, the attachment is ASCII text.</span></span> <span data-ttu-id="22d3a-114">*内容类型: 文本/普通;字符集 = us-ascii 内容传输-编码: 7bit*</span><span class="sxs-lookup"><span data-stu-id="22d3a-114">*Content-type: text/plain; charset=us-ascii Content-Transfer-Encoding: 7bit*</span></span> 
    
- <span data-ttu-id="22d3a-115">如果找到长行或最多 25% 的8位字符, 附件内容是文本, 字符集由区域设置决定。</span><span class="sxs-lookup"><span data-stu-id="22d3a-115">If long lines or up to 25% 8-bit characters are found, the attachment content is text and the character set is determined by the locale.</span></span> <span data-ttu-id="22d3a-116">应从 ISO standard 8859 定义的字符集中选择此设置。</span><span class="sxs-lookup"><span data-stu-id="22d3a-116">It should be chosen from the character sets defined by ISO standard 8859.</span></span> <span data-ttu-id="22d3a-117">*Content-type: text/普通; 字符集 = ISO-8859-1* (例如)</span><span class="sxs-lookup"><span data-stu-id="22d3a-117">*Content-type: text/plain; charset=ISO-8859-1*  (for example)</span></span> 
    
     <span data-ttu-id="22d3a-118">*Content-Transfer-Encoding: quoted-printable*</span><span class="sxs-lookup"><span data-stu-id="22d3a-118">*Content-Transfer-Encoding: quoted-printable*</span></span> 
    
- <span data-ttu-id="22d3a-119">如果 25% 或更多字符设置了高位, 则附件为 binary。</span><span class="sxs-lookup"><span data-stu-id="22d3a-119">If 25% or more of the characters have the high bit set, the attachment is binary.</span></span> <span data-ttu-id="22d3a-120">它是使用 Base64 算法进行编码的。</span><span class="sxs-lookup"><span data-stu-id="22d3a-120">It is encoded using the Base64 algorithm.</span></span> <span data-ttu-id="22d3a-121">*Content-type: application/八进制流* (默认情况下, 基于文件扩展名)</span><span class="sxs-lookup"><span data-stu-id="22d3a-121">*Content-type: application/octet-stream*  (by default; based on file extension)</span></span> 
    
     * <span data-ttu-id="22d3a-122">内容传输编码: base64 \*</span><span class="sxs-lookup"><span data-stu-id="22d3a-122">Content-Transfer-Encoding: base64 \*</span></span> 
    
<span data-ttu-id="22d3a-123">在出站邮件中, 应从文件名的三个字母的扩展名派生内容类型。</span><span class="sxs-lookup"><span data-stu-id="22d3a-123">On outbound messages, the content-type should be derived from the filename's three-letter extension.</span></span> <span data-ttu-id="22d3a-124">系统注册表中存在此映射;在存在一个名为 "Content Type" 的 string 值, 它提供 MIME 内容类型 (如果定义了一个)。</span><span class="sxs-lookup"><span data-stu-id="22d3a-124">This mapping exists in the system registry; under there is a string value named "Content Type" that gives the MIME content type if one is defined.</span></span> <span data-ttu-id="22d3a-125">此示例针对的是 TIFF 图像文件:</span><span class="sxs-lookup"><span data-stu-id="22d3a-125">This example is for a TIFF image file:</span></span>
  
<span data-ttu-id="22d3a-126">HKEY_LOCAL_MACHINE \\</span><span class="sxs-lookup"><span data-stu-id="22d3a-126">HKEY_LOCAL_MACHINE\\</span></span>
  
<span data-ttu-id="22d3a-127">软件列表</span><span class="sxs-lookup"><span data-stu-id="22d3a-127">Software\\</span></span>
  
<span data-ttu-id="22d3a-128">word</span><span class="sxs-lookup"><span data-stu-id="22d3a-128">Microsoft\\</span></span>
  
<span data-ttu-id="22d3a-129">类</span><span class="sxs-lookup"><span data-stu-id="22d3a-129">Classes\\</span></span>
  
<span data-ttu-id="22d3a-130">.tif</span><span class="sxs-lookup"><span data-stu-id="22d3a-130">.tif</span></span>
  
<span data-ttu-id="22d3a-131">内容类型 = "image/tiff"</span><span class="sxs-lookup"><span data-stu-id="22d3a-131">Content Type = "image/tiff"</span></span>
  
<span data-ttu-id="22d3a-132">如果文件扩展名没有映射, 则应使用默认的*应用程序/八进制*流。</span><span class="sxs-lookup"><span data-stu-id="22d3a-132">If there is no mapping for the file extension, the default  *application/octet*  stream should be used.</span></span> 
  
<span data-ttu-id="22d3a-133">在入站邮件中, 附件的内容类型应始终复制到 MAPI 属性**PR_ATTACH_MIME_TAG** ([PidTagAttachMimeTag](pidtagattachmimetag-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="22d3a-133">On inbound messages, the content-type for an attachment should always be copied to the MAPI property **PR_ATTACH_MIME_TAG** ([PidTagAttachMimeTag](pidtagattachmimetag-canonical-property.md)).</span></span> <span data-ttu-id="22d3a-134">即使为附加的文件定义了 filename, 也应在**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 和**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性中使用由 content 类型映射的扩展名。.</span><span class="sxs-lookup"><span data-stu-id="22d3a-134">Even if a filename is defined for an attached file, the extension mapped by the content-type should be used in the **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) and **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) properties.</span></span>
  
<span data-ttu-id="22d3a-135">RFC 821 的*名称*参数已正式弃用。</span><span class="sxs-lookup"><span data-stu-id="22d3a-135">The  *name*  parameter is officially deprecated by RFC 821.</span></span> <span data-ttu-id="22d3a-136">随着标准的发展, Microsoft 将考虑为附加的文件名指定备用映射。</span><span class="sxs-lookup"><span data-stu-id="22d3a-136">As standards evolve, Microsoft will consider specifying an alternate mapping for attached filenames.</span></span> 
  
<span data-ttu-id="22d3a-137">出站附加邮件以 \* Content-type: message//rfc822 \* 邮件的形式发送将以递归方式在正确的位置对其进行编码。</span><span class="sxs-lookup"><span data-stu-id="22d3a-137">Outbound attached messages are sent as \* Content-type: message/rfc822 \*  Messages within attached messages are encoded recursively, in their proper place.</span></span> <span data-ttu-id="22d3a-138">包含*内容类型: 多部分/摘要*的入站邮件内容部件也映射到嵌入的邮件。</span><span class="sxs-lookup"><span data-stu-id="22d3a-138">Inbound message content parts with  *Content-Type: multipart/digest*  are also mapped to embedded messages.</span></span> 
  
<span data-ttu-id="22d3a-139">如果在对邮件内容进行编码时使用 tnef 的 uuencode, 则所有附件属性和内容都在 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="22d3a-139">If uuencode with TNEF is used while encoding message content, all attachment properties and content are in the TNEF stream.</span></span> <span data-ttu-id="22d3a-140">TNEF 本身是一个名为 winmail.dat 的二进制附加文件, 编码为在不使用 TNEF 的 Uuencode 中进行了说明。</span><span class="sxs-lookup"><span data-stu-id="22d3a-140">The TNEF itself is a single, binary attached file named Winmail.dat, encoded as described for Uuencode without TNEF.</span></span>
  
<span data-ttu-id="22d3a-141">如果使用 uuencode 但不使用 TNEF, 则所有附加的文件都将在邮件文本之后被视为 binary 和 uuencoded。</span><span class="sxs-lookup"><span data-stu-id="22d3a-141">If uuencode is used without TNEF, all attached files are treated as binary and uuencoded, following the message text.</span></span> <span data-ttu-id="22d3a-142">uuencode 标头中存在文件名:</span><span class="sxs-lookup"><span data-stu-id="22d3a-142">The file name is present in the uuencode header:</span></span>
  
 <span data-ttu-id="22d3a-143">开始 0755 winmail.dat</span><span class="sxs-lookup"><span data-stu-id="22d3a-143">begin 0755 Winmail.dat</span></span> 
  
 <span data-ttu-id="22d3a-144">...数据 .。。</span><span class="sxs-lookup"><span data-stu-id="22d3a-144">... data ...</span></span> 
  
 <span data-ttu-id="22d3a-145">end</span><span class="sxs-lookup"><span data-stu-id="22d3a-145">end</span></span> 
  
<span data-ttu-id="22d3a-146">附加的邮件将 textized 到邮件正文中。</span><span class="sxs-lookup"><span data-stu-id="22d3a-146">Attached messages are textized into the message text.</span></span> <span data-ttu-id="22d3a-147">始终平展附加的邮件的层次结构;也就是说, 附加的邮件中的邮件将被拉出到顶层。</span><span class="sxs-lookup"><span data-stu-id="22d3a-147">The hierarchy of attached messages is always flattened; that is, messages within attached messages are pulled out to the top level.</span></span>
  
<span data-ttu-id="22d3a-148">嵌入的 OLE 对象将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="22d3a-148">Embedded OLE objects are discarded.</span></span>
  
<span data-ttu-id="22d3a-149">通过使用 TNEF 中的属性**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)), 可以按原义传递附件呈现位置。</span><span class="sxs-lookup"><span data-stu-id="22d3a-149">Attachment rendering positions are transmitted literally, using the property **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) in the TNEF.</span></span> <span data-ttu-id="22d3a-150">如果不使用 TNEF, 它们将丢失。</span><span class="sxs-lookup"><span data-stu-id="22d3a-150">If TNEF is not used, they are lost.</span></span> <span data-ttu-id="22d3a-151">没有呈现位置的传入附件 (包括没有 TNEF 时), 其呈现位置设置为 0xffffffff, 即无位置在邮件文本中。</span><span class="sxs-lookup"><span data-stu-id="22d3a-151">Incoming attachments with no rendering position (including when there is no TNEF) have their rendering position set to 0xFFFFFFFF, that is, no position in the message text.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="22d3a-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22d3a-152">See also</span></span>



[<span data-ttu-id="22d3a-153">将 Internet 邮件属性映射到 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="22d3a-153">Mapping of Internet Mail Attributes to MAPI Properties</span></span>](mapping-of-internet-mail-attributes-to-mapi-properties.md)

