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
# <a name="attached-files-and-messages"></a><span data-ttu-id="7ce29-103">附加的文件和邮件</span><span class="sxs-lookup"><span data-stu-id="7ce29-103">Attached Files and Messages</span></span>

  
  
<span data-ttu-id="7ce29-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ce29-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ce29-105">如果在编码邮件内容时使用 MIME 和 TNEF，则所有附件属性和内容都位于 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="7ce29-105">If MIME with TNEF is used while encoding message content,all attachment properties and content are in the TNEF stream.</span></span> <span data-ttu-id="7ce29-106">TNEF 本身是一个名为 Winmail.dat 的二进制附加文件，其编码方式与没有 TNEF 的 MIME 所述。</span><span class="sxs-lookup"><span data-stu-id="7ce29-106">The TNEF itself is a single, binary attached file named Winmail.dat, encoded as described for MIME without TNEF.</span></span> 
  
<span data-ttu-id="7ce29-107">如果使用 MIME 而不使用 TNEF，则附加文件作为 MIME 邮件内容部分发送。</span><span class="sxs-lookup"><span data-stu-id="7ce29-107">If MIME is used without TNEF, attached files are sent as MIME message content parts.</span></span> <span data-ttu-id="7ce29-108">文件名放置在附件的 *Content-type* 标头的 *name* 参数中。</span><span class="sxs-lookup"><span data-stu-id="7ce29-108">The filename is placed in the  *name*  parameter to the  *Content-type*  header for the attachment.</span></span> <span data-ttu-id="7ce29-109">附件的字符集放置在 *Content-type* 的 *charset* 参数中;它和内容传输编码通过扫描整个附件内容来确定。</span><span class="sxs-lookup"><span data-stu-id="7ce29-109">The character set for the attachment is placed in the  *charset*  parameter to the  *Content-type*  ; it and the content-transfer-encoding are determined by scanning the entire attachment content.</span></span> <span data-ttu-id="7ce29-110">URL 附件会特殊处理：</span><span class="sxs-lookup"><span data-stu-id="7ce29-110">URL attachments are treated specially:</span></span> 
  
- <span data-ttu-id="7ce29-111">如果附件是一个 URL， (扩展名 附加的文件。URL) ，且其中定义的访问模式为匿名 FTP，它编码为外部邮件，文件 (URL) 的内容将复制到外部邮件的标头中。</span><span class="sxs-lookup"><span data-stu-id="7ce29-111">If the attachment is a URL (an attached file with extension .URL), and the access mode defined in it is anonymous FTP, it is encoded as an external message, and the content of the file (the URL) is copied into the header of the external message.</span></span> <span data-ttu-id="7ce29-112">*Content-type： message/external-body; access-type=anon-ftp*  (Content-Transfer-Encoding： 7bit is assumed.) </span><span class="sxs-lookup"><span data-stu-id="7ce29-112">*Content-type: message/external-body; access-type=anon-ftp*  (Content-Transfer-Encoding: 7bit is assumed.)</span></span> 
    
- <span data-ttu-id="7ce29-113">如果只找到 7 位字符且行的长度不超过 140 个字符，则附件为 ASCII 文本。</span><span class="sxs-lookup"><span data-stu-id="7ce29-113">If only 7-bit characters are found and no line exceeds 140 characters in length, the attachment is ASCII text.</span></span> <span data-ttu-id="7ce29-114">*Content-type： text/plain;charset=us-ascii Content-Transfer-Encoding：7bit*</span><span class="sxs-lookup"><span data-stu-id="7ce29-114">*Content-type: text/plain; charset=us-ascii Content-Transfer-Encoding: 7bit*</span></span> 
    
- <span data-ttu-id="7ce29-115">如果找到长行或最多 25% 8 位字符，则附件内容为文本，字符集由区域设置确定。</span><span class="sxs-lookup"><span data-stu-id="7ce29-115">If long lines or up to 25% 8-bit characters are found, the attachment content is text and the character set is determined by the locale.</span></span> <span data-ttu-id="7ce29-116">应从 ISO 标准 8859 定义的字符集选择它。</span><span class="sxs-lookup"><span data-stu-id="7ce29-116">It should be chosen from the character sets defined by ISO standard 8859.</span></span> <span data-ttu-id="7ce29-117">*Content-type： text/plain; charset=ISO-8859-1*  (例如) </span><span class="sxs-lookup"><span data-stu-id="7ce29-117">*Content-type: text/plain; charset=ISO-8859-1*  (for example)</span></span> 
    
     <span data-ttu-id="7ce29-118">*Content-Transfer-Encoding: quoted-printable*</span><span class="sxs-lookup"><span data-stu-id="7ce29-118">*Content-Transfer-Encoding: quoted-printable*</span></span> 
    
- <span data-ttu-id="7ce29-119">如果 25% 或 25% 以上的字符设置了高位，则附件为二进制。</span><span class="sxs-lookup"><span data-stu-id="7ce29-119">If 25% or more of the characters have the high bit set, the attachment is binary.</span></span> <span data-ttu-id="7ce29-120">它使用 Base64 算法进行编码。</span><span class="sxs-lookup"><span data-stu-id="7ce29-120">It is encoded using the Base64 algorithm.</span></span> <span data-ttu-id="7ce29-121">*内容类型：应用程序/octet 流*  (默认;基于文件扩展名) </span><span class="sxs-lookup"><span data-stu-id="7ce29-121">*Content-type: application/octet-stream*  (by default; based on file extension)</span></span> 
    
     * <span data-ttu-id="7ce29-122">Content-Transfer-Encoding： base64 \*</span><span class="sxs-lookup"><span data-stu-id="7ce29-122">Content-Transfer-Encoding: base64 \*</span></span> 
    
<span data-ttu-id="7ce29-123">在出站邮件中，内容类型应派生自文件名的三个字母扩展名。</span><span class="sxs-lookup"><span data-stu-id="7ce29-123">On outbound messages, the content-type should be derived from the filename's three-letter extension.</span></span> <span data-ttu-id="7ce29-124">此映射存在于系统注册表中;under there is a string value named "Content Type" that gives the MIME content type if one is defined.</span><span class="sxs-lookup"><span data-stu-id="7ce29-124">This mapping exists in the system registry; under there is a string value named "Content Type" that gives the MIME content type if one is defined.</span></span> <span data-ttu-id="7ce29-125">此示例适用于 TIFF 图像文件：</span><span class="sxs-lookup"><span data-stu-id="7ce29-125">This example is for a TIFF image file:</span></span>
  
<span data-ttu-id="7ce29-126">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="7ce29-126">HKEY_LOCAL_MACHINE</span></span>\
  
<span data-ttu-id="7ce29-127">Software</span><span class="sxs-lookup"><span data-stu-id="7ce29-127">Software</span></span>\
  
<span data-ttu-id="7ce29-128">Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ce29-128">Microsoft</span></span>\
  
<span data-ttu-id="7ce29-129">Classes</span><span class="sxs-lookup"><span data-stu-id="7ce29-129">Classes</span></span>\
  
<span data-ttu-id="7ce29-130">.tif</span><span class="sxs-lookup"><span data-stu-id="7ce29-130">.tif</span></span>
  
<span data-ttu-id="7ce29-131">内容类型 = "image/tiff"</span><span class="sxs-lookup"><span data-stu-id="7ce29-131">Content Type = "image/tiff"</span></span>
  
<span data-ttu-id="7ce29-132">如果文件扩展名没有映射，则应该使用默认  *应用程序/八进制*  流。</span><span class="sxs-lookup"><span data-stu-id="7ce29-132">If there is no mapping for the file extension, the default  *application/octet*  stream should be used.</span></span> 
  
<span data-ttu-id="7ce29-133">在入站邮件上，附件的内容类型应始终复制到 MAPI 属性PR_ATTACH_MIME_TAG ([PidTagAttachMimeTag](pidtagattachmimetag-canonical-property.md)) 。 </span><span class="sxs-lookup"><span data-stu-id="7ce29-133">On inbound messages, the content-type for an attachment should always be copied to the MAPI property **PR_ATTACH_MIME_TAG** ([PidTagAttachMimeTag](pidtagattachmimetag-canonical-property.md)).</span></span> <span data-ttu-id="7ce29-134">即使为附加文件定义了文件名，也应在 PR_ATTACH_FILENAME ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 和 **PR_ATTACH_EXTENSION** **(** [PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性中使用内容类型映射的扩展名。</span><span class="sxs-lookup"><span data-stu-id="7ce29-134">Even if a filename is defined for an attached file, the extension mapped by the content-type should be used in the **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) and **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) properties.</span></span>
  
<span data-ttu-id="7ce29-135">*RFC* 821 正式弃用 name 参数。</span><span class="sxs-lookup"><span data-stu-id="7ce29-135">The  *name*  parameter is officially deprecated by RFC 821.</span></span> <span data-ttu-id="7ce29-136">随着标准的发展，Microsoft 将考虑指定附加文件名的备用映射。</span><span class="sxs-lookup"><span data-stu-id="7ce29-136">As standards evolve, Microsoft will consider specifying an alternate mapping for attached filenames.</span></span> 
  
<span data-ttu-id="7ce29-137">出站附加邮件以 \* Content-type： message/rfc822 \* 附加邮件中的邮件以递归方式在正确的位置进行编码。</span><span class="sxs-lookup"><span data-stu-id="7ce29-137">Outbound attached messages are sent as \* Content-type: message/rfc822 \*  Messages within attached messages are encoded recursively, in their proper place.</span></span> <span data-ttu-id="7ce29-138">*Content-Type： multipart/digest* 的入站邮件内容部件也映射到嵌入邮件。</span><span class="sxs-lookup"><span data-stu-id="7ce29-138">Inbound message content parts with  *Content-Type: multipart/digest*  are also mapped to embedded messages.</span></span> 
  
<span data-ttu-id="7ce29-139">如果在编码邮件内容时使用 uuencode 和 TNEF，则所有附件属性和内容都位于 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="7ce29-139">If uuencode with TNEF is used while encoding message content, all attachment properties and content are in the TNEF stream.</span></span> <span data-ttu-id="7ce29-140">TNEF 本身是一个名为 Winmail.dat 的二进制附加文件，如 Uuencode（不含 TNEF）所述编码。</span><span class="sxs-lookup"><span data-stu-id="7ce29-140">The TNEF itself is a single, binary attached file named Winmail.dat, encoded as described for Uuencode without TNEF.</span></span>
  
<span data-ttu-id="7ce29-141">如果在没有 TNEF 的情况下使用 uuencode，则邮件文本后的所有附加文件都将被视为二进制文件和 uuencoded 文件。</span><span class="sxs-lookup"><span data-stu-id="7ce29-141">If uuencode is used without TNEF, all attached files are treated as binary and uuencoded, following the message text.</span></span> <span data-ttu-id="7ce29-142">文件名存在于 uuencode 标头中：</span><span class="sxs-lookup"><span data-stu-id="7ce29-142">The file name is present in the uuencode header:</span></span>
  
 <span data-ttu-id="7ce29-143">begin 0755 Winmail.dat</span><span class="sxs-lookup"><span data-stu-id="7ce29-143">begin 0755 Winmail.dat</span></span> 
  
 <span data-ttu-id="7ce29-144">...数据 ...</span><span class="sxs-lookup"><span data-stu-id="7ce29-144">... data ...</span></span> 
  
 <span data-ttu-id="7ce29-145">end</span><span class="sxs-lookup"><span data-stu-id="7ce29-145">end</span></span> 
  
<span data-ttu-id="7ce29-146">附加的邮件会文本化为邮件文本。</span><span class="sxs-lookup"><span data-stu-id="7ce29-146">Attached messages are textized into the message text.</span></span> <span data-ttu-id="7ce29-147">附加邮件的层次结构始终平展;即，附加邮件内的邮件被拉出到顶层。</span><span class="sxs-lookup"><span data-stu-id="7ce29-147">The hierarchy of attached messages is always flattened; that is, messages within attached messages are pulled out to the top level.</span></span>
  
<span data-ttu-id="7ce29-148">丢弃嵌入的 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="7ce29-148">Embedded OLE objects are discarded.</span></span>
  
<span data-ttu-id="7ce29-149">附件呈现位置按字面传输，使用属性PR_ATTACH_RENDERING ( TNEF 中的[PidTagAttachRendering) PidTagAttachRendering。](pidtagattachrendering-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="7ce29-149">Attachment rendering positions are transmitted literally, using the property **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) in the TNEF.</span></span> <span data-ttu-id="7ce29-150">如果未使用 TNEF，则丢失它们。</span><span class="sxs-lookup"><span data-stu-id="7ce29-150">If TNEF is not used, they are lost.</span></span> <span data-ttu-id="7ce29-151">没有呈现位置的传入附件 (包括当没有 TNEF) 则其呈现位置设置为 0xFFFFFFFF，即邮件文本中没有任何位置。</span><span class="sxs-lookup"><span data-stu-id="7ce29-151">Incoming attachments with no rendering position (including when there is no TNEF) have their rendering position set to 0xFFFFFFFF, that is, no position in the message text.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ce29-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ce29-152">See also</span></span>



[<span data-ttu-id="7ce29-153">Internet 邮件属性到 MAPI 属性的映射</span><span class="sxs-lookup"><span data-stu-id="7ce29-153">Mapping of Internet Mail Attributes to MAPI Properties</span></span>](mapping-of-internet-mail-attributes-to-mapi-properties.md)

