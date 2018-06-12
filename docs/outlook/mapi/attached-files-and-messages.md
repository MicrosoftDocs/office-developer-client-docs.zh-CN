---
title: 附加的文件和消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b2f2fb72-23ae-4e0b-a8a1-3b78a1862acb
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 489930b35d24d2691c9b9fbb59b0fa95707a0618
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774544"
---
# <a name="attached-files-and-messages"></a>附加的文件和消息

  
  
**适用于**： Outlook 
  
如果使用 TNEF MIME 编码消息内容时使用，所有附件属性和内容都位于 TNEF 流。 TNEF 本身是名为编码为 MIME 不 TNEF 所述的 Winmail.dat 的单个、 二进制附加的文件。 
  
如果 MIME 使用 TNEF 的情况下，将作为 MIME 邮件内容部分发送附加的文件。 将文件名放附件的*内容类型*标头的*名称*参数中。 附件的字符集放置在*内容类型*; *charset*参数由扫描整个附件内容确定和内容传输编码。 要进行专门处理 URL 附件： 
  
- 如果附件是 URL （附加文件扩展名。URL)，在其中定义的访问模式是匿名 FTP、 作为外部邮件，进行编码和文件 (URL) 的内容复制到外部邮件的标头。 *内容类型： 邮件/外部正文; 访问类型 = 匿名 ftp* (内容传送编码： 假定 7 位。) 
    
- 如果只找到 7 位字符，并且没有行超过 140 个字符的长度，附件是 ASCII 文本。 *内容类型： text/plain;charset = 我们 ascii 内容传输编码： 7 位* 
    
- 如果长行或向上 25 %8 位找到字符，附件内容为文字，由区域设置来确定的字符集。 从由 ISO 标准 8859 定义的字符集，应选择它。 *Content-type: text/plain; charset = ISO-8859-1* （示例） 
    
     *内容传送编码： 用引号括起来打印* 
    
- 25%或多个字符有较高的位设置，如果附件是二进制。 它是使用 Base64 算法进行编码。 *内容类型： 应用程序/八进制流* （默认情况下; 基于文件扩展名） 
    
     * 内容传送编码： base64 * 
    
出站邮件，应从三个字母扩展名派生内容类型。 在系统注册表; 存在此映射这里是一个 string 值，名为"内容类型"提供的 MIME 内容类型，如果已定义。 本示例是 TIFF 图像文件：
  
HKEY_LOCAL_MACHINE\
  
Software\
  
Microsoft\
  
Classes\
  
.tif
  
内容类型 ="图像/tiff"
  
如果没有为文件扩展名映射，则应使用默认*应用程序/八进制*流。 
  
对入站邮件的附件的内容类型应始终将复制到 MAPI 属性**PR_ATTACH_MIME_TAG** ([PidTagAttachMimeTag](pidtagattachmimetag-canonical-property.md))。 即使附加文件定义文件名，则应**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 和**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性中使用的内容类型映射的扩展.
  
*Name*参数正式遗弃 RFC 821。 在标准的发展，Microsoft 将请考虑指定附加文件名备用映射。 
  
作为发送出站连接的邮件 * 内容类型： 邮件/附加了 rfc822 * 附加的邮件中的邮件的编码以递归方式，在其适当的位置。 入站邮件内容部件*内容类型： 多部分/摘要*还会将其映射到嵌入邮件。 
  
如果使用 TNEF 的 uuencode 编码消息内容时使用，所有附件属性和内容都位于 TNEF 流。 TNEF 本身是名为 Winmail.dat，如下所述的 Uuencode 不 TNEF 编码的单个、 二进制附加的文件。
  
如果 uuencode 使用 TNEF 的情况下，所有附加的文件将被视为二进制和 uuencoded，关注消息文本。 Uuencode 标头中存在的文件名将：
  
 开始 0755 Winmail.dat 
  
 ...数据... 
  
 end 
  
附加的邮件被 textized 到消息文本。 始终平展层次结构的附加邮件;即附加的邮件中的邮件将提取出的顶层。
  
嵌入的 OLE 对象将被丢弃。
  
使用 tnef 属性**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 按字面本身，传输附件呈现位置。 如果不使用 TNEF，则会丢失。 具有不呈现位置 （包括无 TNEF 时） 的传入附件具有消息文本中的没有位置设置为 0xFFFFFFFF，即，其呈现位置。
  
## <a name="see-also"></a>另请参阅



[映射到 MAPI 属性的 Internet 邮件属性](mapping-of-internet-mail-attributes-to-mapi-properties.md)

