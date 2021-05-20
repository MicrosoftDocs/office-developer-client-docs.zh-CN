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
# <a name="attached-files-and-messages"></a>附加的文件和邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果在编码邮件内容时使用 MIME 和 TNEF，则所有附件属性和内容都位于 TNEF 流中。 TNEF 本身是一个名为 Winmail.dat 的二进制附加文件，其编码方式与没有 TNEF 的 MIME 所述。 
  
如果使用 MIME 而不使用 TNEF，则附加文件作为 MIME 邮件内容部分发送。 文件名放置在附件的 *Content-type* 标头的 *name* 参数中。 附件的字符集放置在 *Content-type* 的 *charset* 参数中;它和内容传输编码通过扫描整个附件内容来确定。 URL 附件会特殊处理： 
  
- 如果附件是一个 URL， (扩展名 附加的文件。URL) ，且其中定义的访问模式为匿名 FTP，它编码为外部邮件，文件 (URL) 的内容将复制到外部邮件的标头中。 *Content-type： message/external-body; access-type=anon-ftp*  (Content-Transfer-Encoding： 7bit is assumed.)  
    
- 如果只找到 7 位字符且行的长度不超过 140 个字符，则附件为 ASCII 文本。 *Content-type： text/plain;charset=us-ascii Content-Transfer-Encoding：7bit* 
    
- 如果找到长行或最多 25% 8 位字符，则附件内容为文本，字符集由区域设置确定。 应从 ISO 标准 8859 定义的字符集选择它。 *Content-type： text/plain; charset=ISO-8859-1*  (例如)  
    
     *Content-Transfer-Encoding: quoted-printable* 
    
- 如果 25% 或 25% 以上的字符设置了高位，则附件为二进制。 它使用 Base64 算法进行编码。 *内容类型：应用程序/octet 流*  (默认;基于文件扩展名)  
    
     * Content-Transfer-Encoding： base64 * 
    
在出站邮件中，内容类型应派生自文件名的三个字母扩展名。 此映射存在于系统注册表中;under there is a string value named "Content Type" that gives the MIME content type if one is defined. 此示例适用于 TIFF 图像文件：
  
HKEY_LOCAL_MACHINE\
  
Software\
  
Microsoft\
  
Classes\
  
.tif
  
内容类型 = "image/tiff"
  
如果文件扩展名没有映射，则应该使用默认  *应用程序/八进制*  流。 
  
在入站邮件上，附件的内容类型应始终复制到 MAPI 属性PR_ATTACH_MIME_TAG ([PidTagAttachMimeTag](pidtagattachmimetag-canonical-property.md)) 。  即使为附加文件定义了文件名，也应在 PR_ATTACH_FILENAME ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 和 **PR_ATTACH_EXTENSION** **(** [PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性中使用内容类型映射的扩展名。
  
*RFC* 821 正式弃用 name 参数。 随着标准的发展，Microsoft 将考虑指定附加文件名的备用映射。 
  
出站附加邮件以 * Content-type： message/rfc822 * 附加邮件中的邮件以递归方式在正确的位置进行编码。 *Content-Type： multipart/digest* 的入站邮件内容部件也映射到嵌入邮件。 
  
如果在编码邮件内容时使用 uuencode 和 TNEF，则所有附件属性和内容都位于 TNEF 流中。 TNEF 本身是一个名为 Winmail.dat 的二进制附加文件，如 Uuencode（不含 TNEF）所述编码。
  
如果在没有 TNEF 的情况下使用 uuencode，则邮件文本后的所有附加文件都将被视为二进制文件和 uuencoded 文件。 文件名存在于 uuencode 标头中：
  
 begin 0755 Winmail.dat 
  
 ...数据 ... 
  
 end 
  
附加的邮件会文本化为邮件文本。 附加邮件的层次结构始终平展;即，附加邮件内的邮件被拉出到顶层。
  
丢弃嵌入的 OLE 对象。
  
附件呈现位置按字面传输，使用属性PR_ATTACH_RENDERING ( TNEF 中的[PidTagAttachRendering) PidTagAttachRendering。](pidtagattachrendering-canonical-property.md) 如果未使用 TNEF，则丢失它们。 没有呈现位置的传入附件 (包括当没有 TNEF) 则其呈现位置设置为 0xFFFFFFFF，即邮件文本中没有任何位置。
  
## <a name="see-also"></a>另请参阅



[Internet 邮件属性到 MAPI 属性的映射](mapping-of-internet-mail-attributes-to-mapi-properties.md)

