---
title: 分析 POP3 帐户的邮件下载历史记录
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 394e1430-04d6-4d61-be13-eb695309fa73
description: 本主题介绍 pop3 BLOB 的结构, 该 BLOB 表示 pop3 帐户的邮件下载历史记录, 用于标识已在该帐户上下载或删除的邮件。
ms.openlocfilehash: 44a799f6b6fbe2a2841522c18405149a470b0236
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327757"
---
# <a name="parsing-the-message-download-history-for-a-pop3-account"></a>分析 POP3 帐户的邮件下载历史记录

本主题介绍 pop3 BLOB 的结构, 该 BLOB 表示 pop3 帐户的邮件下载历史记录, 用于标识已在该帐户上下载或删除的邮件。

<a name="OL15Con_AuxRef_ParsingMsgsHistory_WhyParseHistory"> </a>

## <a name="why-parse-the-message-download-history"></a>为什么分析邮件下载历史记录？

Outlook 的邮局协议 (POP) 提供程序允许用户在其本地设备上检索和下载新的电子邮件, 并随后在邮件服务器上保留或删除这些电子邮件。 当邮件客户端检查要下载的新邮件时, 它必须能够识别和下载该收件箱的新邮件。 邮件客户端通过首先使用 UIDL (唯一 ID 列表) 命令来获取已传递到该收件箱的每封邮件的映射, 以获取唯一标识符 (UID) 的映射。 客户端还会获取邮件下载历史记录, 以了解已为该客户端上的 "收件箱" 下载或删除的邮件。 通过使用邮件 UID 映射和下载历史记录, 客户端可以将历史记录中缺少的那些邮件标识为新的, 因此应下载这些邮件。
  
要获取收件箱的邮件下载历史记录, 请执行以下操作:
  
- 按照[查找 pop3 帐户的邮件下载历史记录](locating-the-message-download-history-for-a-pop3-account.md)中的步骤查找[PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx)属性, 该属性包含一个二进制大型对象 (BLOB), 该对象代表 POP3 帐户的邮件历史记录。 
    
- 阅读本主题, 其中介绍了 BLOB 的结构, 并显示了一个示例 BLOB, 用于标识已为 POP3 帐户的收件箱下载或删除的邮件。

<a name="OL15Con_AuxRef_ParsingMsgsHistory_BLOBStructure"> </a>

## <a name="pop-blob-structure"></a>POP BLOB 结构

POP BLOB 结构 (如表1中所述) 以两个字段 " **Version** " 和 "**计数**" 开头, 后跟 "资源标记数", 其中每个字段的**计数**都是以 null 结尾的。 
  
**表1。表示 POP3 帐户的邮件下载历史记录的 BLOB 的结构**

|**BLOB 中的字段**|**Size**|**说明**|
|:-----|:-----|:-----|
|**版本** <br/> |2 个字节  <br/> |必须为 3 (**PBLOB_VERSION_NUM**)。  <br/> |
|**Count** <br/> |2 个字节  <br/> |此 BLOB 中的资源标记数。  <br/> |
|资源标记  <br/> |变量  <br/> |0个或更多以 null 结尾的 utf-8 字符串, 用于对资源标记进行编码。 以 null 结尾的字符串的数目必须与**Count**相匹配。  <br/> |
   
每个资源标记指定应用于邮件的操作、有关操作的一些日期时间元数据, 以及对邮件的 UID 进行编码。 资源标记字符串的格式按如下方式分解, 并在表2中进一步说明。 
  
`Ocyyyymmddhhmmssuuu...`
  
**表2。资源标记的结构**

|**资源标记中的字段**|**Size**|**Description**|
|:-----|:-----|:-----|
| `O` <br/> |1个字符  <br/> |对电子邮件执行的操作。 该值必须是 "+"、"-" 或 "&amp;", 分别表示成功的获取、删除或获取和删除操作。  <br/> |
| `c` <br/> |1个字符  <br/> |操作中涉及的邮件内容部分。 该值必须是 ""、"h" 或 "b", 分别表示无、头或正文的内容。  <br/> |
| `yyyy` <br/> |4个字符  <br/> |此运算的四位数年份。  <br/> |
| `MM` <br/> |2个字符  <br/> |运算的两位数月份。  <br/> |
| `dd` <br/> |2个字符  <br/> |操作的两位数日期。  <br/> |
| `hh` <br/> |2个字符  <br/> |运算的两位数的小时数。  <br/> |
| `mm` <br/> |2个字符  <br/> |运算的两位数分钟数。  <br/> |
| `ss` <br/> |2个字符  <br/> |运算的两位数秒数。  <br/> |
| `uuu…` <br/> |可变长度  <br/> |邮件的编码 UID。  <br/> |

<a name="OL15Con_AuxRef_ParsingMsgsHistory_Example"> </a>

## <a name="example"></a>示例

图1显示了一个 BLOB, 该示例表示 POP 帐户的邮件下载历史记录。 
  
**图1。POP3 帐户的邮件下载历史记录的示例 BLOB 结构**

![用于 POP3 帐户的消息下载历史记录的 BLOB](media/OL15Con_AuxRef_ParsingMsgsHistory_Blob.gif)
  
根据表1和表2中所述的结构, 此 BLOB 表示23封电子邮件的下载历史记录。
  
若要分析每个资源标记中的原始 UID, 请注意, uid 遵循以下编码: uid 中的字符主要是字母数字字符, 并且每个非字母数字字符前面都有 ASCII 字符 "$" (0x24)。 因此, ASCII 字符 $ 2d 代表非字母数字字符 "-"。 图2显示了首先将资源标记1中的原始 UID 转换为 ASCII 表示形式的示例, 然后转换以 "$" 开头的任何非字母数字字符, 以生成实际的 UID:
  
`0BC535DB-EA63-11E1-A75C-00215AD7BB74`
  
**图2。将资源标记中的原始 UID 转换为实际的邮件 UID**

![将 BLOB 中的原始 UID 转换为实际消息 UID](media/OL15Con_AuxRef_ParsingMsgsHistory_BlobRscTag.gif)
  
若要解释此 BLOB 中的资源标记 1, 请参阅 13:11:38 `0BC535DB-EA63-11E1-A75C-00215AD7BB74`在2012年9月6日成功检索 UID 为的邮件。 
  
您可以同样分析该 BLOB 的其余22个资源标记。
  
## <a name="see-also"></a>另请参阅
<a name="OL15Con_AuxRef_ParsingMsgsHistory_AdditionalRsc"> </a>

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md)    
- [查找一个 POP3 帐户的消息下载历史记录](locating-the-message-download-history-for-a-pop3-account.md)    
- [分析 POP3 UIDL 历史记录](https://blogs.msdn.com/b/stephen_griffin/archive/2012/12/04/parsing-the-pop3-uidl-history.aspx)
    

