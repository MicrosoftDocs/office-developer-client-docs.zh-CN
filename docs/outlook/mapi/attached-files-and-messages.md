---
title: 附加的文件和邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b2f2fb72-23ae-4e0b-a8a1-3b78a1862acb
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d5b37ea2e254e05ada3214309f58147e92f46393
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566829"
---
# <a name="attached-files-and-messages"></a><span data-ttu-id="41854-103">附加的文件和邮件</span><span class="sxs-lookup"><span data-stu-id="41854-103">Attached Files and Messages</span></span>

  
  
<span data-ttu-id="41854-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="41854-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="41854-105">如果使用 TNEF MIME 编码消息内容时使用，所有附件属性和内容都位于 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="41854-105">If MIME with TNEF is used while encoding message content,all attachment properties and content are in the TNEF stream.</span></span> <span data-ttu-id="41854-106">TNEF 本身是名为编码为 MIME 不 TNEF 所述的 Winmail.dat 的单个、 二进制附加的文件。</span><span class="sxs-lookup"><span data-stu-id="41854-106">The TNEF itself is a single, binary attached file named Winmail.dat, encoded as described for MIME without TNEF.</span></span> 
  
<span data-ttu-id="41854-107">如果 MIME 使用 TNEF 的情况下，将作为 MIME 邮件内容部分发送附加的文件。</span><span class="sxs-lookup"><span data-stu-id="41854-107">If MIME is used without TNEF, attached files are sent as MIME message content parts.</span></span> <span data-ttu-id="41854-108">将文件名放附件的*内容类型*标头的*名称*参数中。</span><span class="sxs-lookup"><span data-stu-id="41854-108">The filename is placed in the  *name*  parameter to the  *Content-type*  header for the attachment.</span></span> <span data-ttu-id="41854-109">附件的字符集放置在*内容类型*; *charset*参数由扫描整个附件内容确定和内容传输编码。</span><span class="sxs-lookup"><span data-stu-id="41854-109">The character set for the attachment is placed in the  *charset*  parameter to the  *Content-type*  ; it and the content-transfer-encoding are determined by scanning the entire attachment content.</span></span> <span data-ttu-id="41854-110">要进行专门处理 URL 附件：</span><span class="sxs-lookup"><span data-stu-id="41854-110">URL attachments are treated specially:</span></span> 
  
- <span data-ttu-id="41854-111">如果附件是 URL （附加文件扩展名。URL)，在其中定义的访问模式是匿名 FTP、 作为外部邮件，进行编码和文件 (URL) 的内容复制到外部邮件的标头。</span><span class="sxs-lookup"><span data-stu-id="41854-111">If the attachment is a URL (an attached file with extension .URL), and the access mode defined in it is anonymous FTP, it is encoded as an external message, and the content of the file (the URL) is copied into the header of the external message.</span></span> <span data-ttu-id="41854-112">*内容类型： 邮件/外部正文; 访问类型 = 匿名 ftp* (内容传送编码： 假定 7 位。)</span><span class="sxs-lookup"><span data-stu-id="41854-112">*Content-type: message/external-body; access-type=anon-ftp*  (Content-Transfer-Encoding: 7bit is assumed.)</span></span> 
    
- <span data-ttu-id="41854-113">如果只找到 7 位字符，并且没有行超过 140 个字符的长度，附件是 ASCII 文本。</span><span class="sxs-lookup"><span data-stu-id="41854-113">If only 7-bit characters are found and no line exceeds 140 characters in length, the attachment is ASCII text.</span></span> <span data-ttu-id="41854-114">*内容类型： text/plain;charset = 我们 ascii 内容传输编码： 7 位*</span><span class="sxs-lookup"><span data-stu-id="41854-114">*Content-type: text/plain; charset=us-ascii Content-Transfer-Encoding: 7bit*</span></span> 
    
- <span data-ttu-id="41854-115">如果长行或向上 25 %8 位找到字符，附件内容为文字，由区域设置来确定的字符集。</span><span class="sxs-lookup"><span data-stu-id="41854-115">If long lines or up to 25% 8-bit characters are found, the attachment content is text and the character set is determined by the locale.</span></span> <span data-ttu-id="41854-116">从由 ISO 标准 8859 定义的字符集，应选择它。</span><span class="sxs-lookup"><span data-stu-id="41854-116">It should be chosen from the character sets defined by ISO standard 8859.</span></span> <span data-ttu-id="41854-117">*Content-type: text/plain; charset = ISO-8859-1* （示例）</span><span class="sxs-lookup"><span data-stu-id="41854-117">*Content-type: text/plain; charset=ISO-8859-1*  (for example)</span></span> 
    
     <span data-ttu-id="41854-118">*Content-Transfer-Encoding: quoted-printable*</span><span class="sxs-lookup"><span data-stu-id="41854-118">*Content-Transfer-Encoding: quoted-printable*</span></span> 
    
- <span data-ttu-id="41854-119">25%或多个字符有较高的位设置，如果附件是二进制。</span><span class="sxs-lookup"><span data-stu-id="41854-119">If 25% or more of the characters have the high bit set, the attachment is binary.</span></span> <span data-ttu-id="41854-120">它是使用 Base64 算法进行编码。</span><span class="sxs-lookup"><span data-stu-id="41854-120">It is encoded using the Base64 algorithm.</span></span> <span data-ttu-id="41854-121">*内容类型： 应用程序/八进制流* （默认情况下; 基于文件扩展名）</span><span class="sxs-lookup"><span data-stu-id="41854-121">*Content-type: application/octet-stream*  (by default; based on file extension)</span></span> 
    
     * <span data-ttu-id="41854-122">内容传送编码： base64 \*</span><span class="sxs-lookup"><span data-stu-id="41854-122">Content-Transfer-Encoding: base64 \*</span></span> 
    
<span data-ttu-id="41854-123">出站邮件，应从三个字母扩展名派生内容类型。</span><span class="sxs-lookup"><span data-stu-id="41854-123">On outbound messages, the content-type should be derived from the filename's three-letter extension.</span></span> <span data-ttu-id="41854-124">在系统注册表; 存在此映射这里是一个 string 值，名为"内容类型"提供的 MIME 内容类型，如果已定义。</span><span class="sxs-lookup"><span data-stu-id="41854-124">This mapping exists in the system registry; under there is a string value named "Content Type" that gives the MIME content type if one is defined.</span></span> <span data-ttu-id="41854-125">本示例是 TIFF 图像文件：</span><span class="sxs-lookup"><span data-stu-id="41854-125">This example is for a TIFF image file:</span></span>
  
<span data-ttu-id="41854-126">HKEY_LOCAL_MACHINE\\</span><span class="sxs-lookup"><span data-stu-id="41854-126">HKEY_LOCAL_MACHINE\\</span></span>
  
<span data-ttu-id="41854-127">Software\\</span><span class="sxs-lookup"><span data-stu-id="41854-127">Software\\</span></span>
  
<span data-ttu-id="41854-128">Microsoft\\</span><span class="sxs-lookup"><span data-stu-id="41854-128">Microsoft\\</span></span>
  
<span data-ttu-id="41854-129">Classes\\</span><span class="sxs-lookup"><span data-stu-id="41854-129">Classes\\</span></span>
  
<span data-ttu-id="41854-130">.tif</span><span class="sxs-lookup"><span data-stu-id="41854-130">.tif</span></span>
  
<span data-ttu-id="41854-131">内容类型 ="图像/tiff"</span><span class="sxs-lookup"><span data-stu-id="41854-131">Content Type = "image/tiff"</span></span>
  
<span data-ttu-id="41854-132">如果没有为文件扩展名映射，则应使用默认*应用程序/八进制*流。</span><span class="sxs-lookup"><span data-stu-id="41854-132">If there is no mapping for the file extension, the default  *application/octet*  stream should be used.</span></span> 
  
<span data-ttu-id="41854-133">对入站邮件的附件的内容类型应始终将复制到 MAPI 属性**PR_ATTACH_MIME_TAG** ([PidTagAttachMimeTag](pidtagattachmimetag-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="41854-133">On inbound messages, the content-type for an attachment should always be copied to the MAPI property **PR_ATTACH_MIME_TAG** ([PidTagAttachMimeTag](pidtagattachmimetag-canonical-property.md)).</span></span> <span data-ttu-id="41854-134">即使附加文件定义文件名，则应**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 和**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性中使用的内容类型映射的扩展.</span><span class="sxs-lookup"><span data-stu-id="41854-134">Even if a filename is defined for an attached file, the extension mapped by the content-type should be used in the **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) and **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) properties.</span></span>
  
<span data-ttu-id="41854-135">*Name*参数正式遗弃 RFC 821。</span><span class="sxs-lookup"><span data-stu-id="41854-135">The  *name*  parameter is officially deprecated by RFC 821.</span></span> <span data-ttu-id="41854-136">在标准的发展，Microsoft 将请考虑指定附加文件名备用映射。</span><span class="sxs-lookup"><span data-stu-id="41854-136">As standards evolve, Microsoft will consider specifying an alternate mapping for attached filenames.</span></span> 
  
<span data-ttu-id="41854-137">作为发送出站连接的邮件 * 内容类型： 邮件/附加了 rfc822 * 附加的邮件中的邮件的编码以递归方式，在其适当的位置。</span><span class="sxs-lookup"><span data-stu-id="41854-137">Outbound attached messages are sent as * Content-type: message/rfc822 *  Messages within attached messages are encoded recursively, in their proper place.</span></span> <span data-ttu-id="41854-138">入站邮件内容部件*内容类型： 多部分/摘要*还会将其映射到嵌入邮件。</span><span class="sxs-lookup"><span data-stu-id="41854-138">Inbound message content parts with  *Content-Type: multipart/digest*  are also mapped to embedded messages.</span></span> 
  
<span data-ttu-id="41854-139">如果使用 TNEF 的 uuencode 编码消息内容时使用，所有附件属性和内容都位于 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="41854-139">If uuencode with TNEF is used while encoding message content, all attachment properties and content are in the TNEF stream.</span></span> <span data-ttu-id="41854-140">TNEF 本身是名为 Winmail.dat，如下所述的 Uuencode 不 TNEF 编码的单个、 二进制附加的文件。</span><span class="sxs-lookup"><span data-stu-id="41854-140">The TNEF itself is a single, binary attached file named Winmail.dat, encoded as described for Uuencode without TNEF.</span></span>
  
<span data-ttu-id="41854-141">如果 uuencode 使用 TNEF 的情况下，所有附加的文件将被视为二进制和 uuencoded，关注消息文本。</span><span class="sxs-lookup"><span data-stu-id="41854-141">If uuencode is used without TNEF, all attached files are treated as binary and uuencoded, following the message text.</span></span> <span data-ttu-id="41854-142">Uuencode 标头中存在的文件名将：</span><span class="sxs-lookup"><span data-stu-id="41854-142">The file name is present in the uuencode header:</span></span>
  
 <span data-ttu-id="41854-143">开始 0755 Winmail.dat</span><span class="sxs-lookup"><span data-stu-id="41854-143">begin 0755 Winmail.dat</span></span> 
  
 <span data-ttu-id="41854-144">...数据...</span><span class="sxs-lookup"><span data-stu-id="41854-144">... data ...</span></span> 
  
 <span data-ttu-id="41854-145">end</span><span class="sxs-lookup"><span data-stu-id="41854-145">end</span></span> 
  
<span data-ttu-id="41854-146">附加的邮件被 textized 到消息文本。</span><span class="sxs-lookup"><span data-stu-id="41854-146">Attached messages are textized into the message text.</span></span> <span data-ttu-id="41854-147">始终平展层次结构的附加邮件;即附加的邮件中的邮件将提取出的顶层。</span><span class="sxs-lookup"><span data-stu-id="41854-147">The hierarchy of attached messages is always flattened; that is, messages within attached messages are pulled out to the top level.</span></span>
  
<span data-ttu-id="41854-148">嵌入的 OLE 对象将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="41854-148">Embedded OLE objects are discarded.</span></span>
  
<span data-ttu-id="41854-149">使用 tnef 属性**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 按字面本身，传输附件呈现位置。</span><span class="sxs-lookup"><span data-stu-id="41854-149">Attachment rendering positions are transmitted literally, using the property **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) in the TNEF.</span></span> <span data-ttu-id="41854-150">如果不使用 TNEF，则会丢失。</span><span class="sxs-lookup"><span data-stu-id="41854-150">If TNEF is not used, they are lost.</span></span> <span data-ttu-id="41854-151">具有不呈现位置 （包括无 TNEF 时） 的传入附件具有消息文本中的没有位置设置为 0xFFFFFFFF，即，其呈现位置。</span><span class="sxs-lookup"><span data-stu-id="41854-151">Incoming attachments with no rendering position (including when there is no TNEF) have their rendering position set to 0xFFFFFFFF, that is, no position in the message text.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41854-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41854-152">See also</span></span>



[<span data-ttu-id="41854-153">将 Internet Mail 属性映射到 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="41854-153">Mapping of Internet Mail Attributes to MAPI Properties</span></span>](mapping-of-internet-mail-attributes-to-mapi-properties.md)

