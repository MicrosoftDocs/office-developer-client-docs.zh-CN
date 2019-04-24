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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318128"
---
# <a name="attached-files-and-messages"></a>附加的文件和邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果在对邮件内容进行编码时使用了带有 TNEF 的 MIME, 则所有附件属性和内容都在 TNEF 流中。 TNEF 本身是一个名为 winmail.dat 的二进制附加文件, 编码为对不带 TNEF 的 MIME 所做的编码。 
  
如果在没有 TNEF 的情况下使用 MIME, 附加的文件将作为 MIME 邮件内容部分发送。 filename 放置在附件的*内容类型*标头的*name*参数中。 将附件的字符集放在*内容类型*的*字符集*参数中;通过扫描整个附件内容来确定它和内容传送编码。 特殊处理 URL 附件: 
  
- 如果附件是 URL (扩展名为的附加文件)。URL), 并且在其中定义的访问模式是匿名 FTP, 它被编码为外部邮件, 并且将文件的内容 (URL) 复制到外部邮件的标头中。 *Content-type: message/external-body; 访问类型 = anon-ftp* (内容传输编码: 假定为7bit。) 
    
- 如果仅找到7位字符, 并且没有任何行的长度超过140个字符, 则附件为 ASCII 文本。 *内容类型: 文本/普通;字符集 = us-ascii 内容传输-编码: 7bit* 
    
- 如果找到长行或最多 25% 的8位字符, 附件内容是文本, 字符集由区域设置决定。 应从 ISO standard 8859 定义的字符集中选择此设置。 *Content-type: text/普通; 字符集 = ISO-8859-1* (例如) 
    
     *Content-Transfer-Encoding: quoted-printable* 
    
- 如果 25% 或更多字符设置了高位, 则附件为 binary。 它是使用 Base64 算法进行编码的。 *Content-type: application/八进制流* (默认情况下, 基于文件扩展名) 
    
     * 内容传输编码: base64 * 
    
在出站邮件中, 应从文件名的三个字母的扩展名派生内容类型。 系统注册表中存在此映射;在存在一个名为 "Content Type" 的 string 值, 它提供 MIME 内容类型 (如果定义了一个)。 此示例针对的是 TIFF 图像文件:
  
HKEY_LOCAL_MACHINE \
  
软件列表
  
word
  
类
  
.tif
  
内容类型 = "image/tiff"
  
如果文件扩展名没有映射, 则应使用默认的*应用程序/八进制*流。 
  
在入站邮件中, 附件的内容类型应始终复制到 MAPI 属性**PR_ATTACH_MIME_TAG** ([PidTagAttachMimeTag](pidtagattachmimetag-canonical-property.md))。 即使为附加的文件定义了 filename, 也应在**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 和**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性中使用由 content 类型映射的扩展名。.
  
RFC 821 的*名称*参数已正式弃用。 随着标准的发展, Microsoft 将考虑为附加的文件名指定备用映射。 
  
出站附加邮件以 * Content-type: message//rfc822 * 邮件的形式发送将以递归方式在正确的位置对其进行编码。 包含*内容类型: 多部分/摘要*的入站邮件内容部件也映射到嵌入的邮件。 
  
如果在对邮件内容进行编码时使用 tnef 的 uuencode, 则所有附件属性和内容都在 TNEF 流中。 TNEF 本身是一个名为 winmail.dat 的二进制附加文件, 编码为在不使用 TNEF 的 Uuencode 中进行了说明。
  
如果使用 uuencode 但不使用 TNEF, 则所有附加的文件都将在邮件文本之后被视为 binary 和 uuencoded。 uuencode 标头中存在文件名:
  
 开始 0755 winmail.dat 
  
 ...数据 .。。 
  
 end 
  
附加的邮件将 textized 到邮件正文中。 始终平展附加的邮件的层次结构;也就是说, 附加的邮件中的邮件将被拉出到顶层。
  
嵌入的 OLE 对象将被丢弃。
  
通过使用 TNEF 中的属性**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)), 可以按原义传递附件呈现位置。 如果不使用 TNEF, 它们将丢失。 没有呈现位置的传入附件 (包括没有 TNEF 时), 其呈现位置设置为 0xffffffff, 即无位置在邮件文本中。
  
## <a name="see-also"></a>另请参阅



[将 Internet 邮件属性映射到 MAPI 属性](mapping-of-internet-mail-attributes-to-mapi-properties.md)

