---
title: 分析 POP3 帐户的邮件下载历史记录
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 394e1430-04d6-4d61-be13-eb695309fa73
description: 本主题介绍 POP3 BLOB 的结构，该 BLOB 表示 POP3 帐户的邮件下载历史记录，用于标识已在该帐户上下载或删除的邮件。
ms.openlocfilehash: 44a799f6b6fbe2a2841522c18405149a470b0236
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327757"
---
# <a name="parsing-the-message-download-history-for-a-pop3-account"></a>分析 POP3 帐户的邮件下载历史记录

本主题介绍 POP3 BLOB 的结构，该 BLOB 表示 POP3 帐户的邮件下载历史记录，用于标识已在该帐户上下载或删除的邮件。

<a name="OL15Con_AuxRef_ParsingMsgsHistory_WhyParseHistory"> </a>

## <a name="why-parse-the-message-download-history"></a>为什么分析邮件下载历史记录？

post Office Protocol (POP) provider for Outlook 允许用户检索和下载其本地设备上的新电子邮件，并随后在邮件服务器上保留或删除这些电子邮件。 当邮件客户端检查是否下载新邮件时，它必须能够仅识别并下载该收件箱的新邮件。 为此，邮件客户端首先使用 UIDL (唯一 ID 列表) 命令获取曾经传递到该收件箱的每个邮件的映射，该唯一标识符 (UID) 。 客户端还获取该客户端上的收件箱已下载或删除的邮件的邮件下载历史记录。 然后，使用消息 UID 映射和下载历史记录，客户端可以将历史记录中不存在的消息标识为新消息，因此应下载这些消息。
  
若要获取收件箱的邮件下载历史记录，
  
- 按照查找 [POP3](locating-the-message-download-history-for-a-pop3-account.md) 帐户的邮件下载历史记录中的步骤查找 [PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx) 属性，该属性包含二进制大型对象 (BLOB) ，代表 POP3 帐户的邮件历史记录。 
    
- 阅读本主题，它描述 BLOB 的结构，并演示一个示例 BLOB，以标识已针对 POP3 帐户的收件箱下载或删除的邮件。

<a name="OL15Con_AuxRef_ParsingMsgsHistory_BLOBStructure"> </a>

## <a name="pop-blob-structure"></a>POP BLOB 结构

如表 1 中所述，POP BLOB 结构以两个字段 **Version** 和 **Count** 开头，后跟资源标记的 **Count** 数量，每个字段以 null 结束。 
  
**表 1.表示 POP3 帐户的邮件下载历史记录的 BLOB 的结构**

|**BLOB 中的字段**|**大小**|**说明**|
|:-----|:-----|:-----|
|**版本** <br/> |2 个字节  <br/> |必须为 3 **(PBLOB_VERSION_NUM) 。**  <br/> |
|**Count** <br/> |2 个字节  <br/> |此 BLOB 中的资源标记数。  <br/> |
|资源标记  <br/> |变量  <br/> |对资源标记进行编码的 0 个或多个以 null 结束的 UTF-8 字符串。 以 null 结束的字符串数必须与 **Count 匹配**。  <br/> |
   
每个资源标记指定应用于邮件的操作、有关该操作的一些日期时间元数据，并编码邮件的 UID。 资源标记字符串的格式按如下所示进行细分，表 2 中对此进行了进一步说明。 
  
`Ocyyyymmddhhmmssuuu...`
  
**表 2.资源标记的结构**

|**资源标记中的字段**|**大小**|**说明**|
|:-----|:-----|:-----|
| `O` <br/> |1 个字符  <br/> |对电子邮件执行的操作。 该值必须为"+"、"-"或""，分别表示成功执行 &amp; get、delete 或 get-and-delete 操作。  <br/> |
| `c` <br/> |1 个字符  <br/> |操作中涉及的消息内容部分。 该值必须为""、"h"或"b"，分别指示 none、header 或 body 的内容。  <br/> |
| `yyyy` <br/> |4 个字符  <br/> |四位数的操作年份。  <br/> |
| `MM` <br/> |2 个字符  <br/> |此操作的两位数月份。  <br/> |
| `dd` <br/> |2 个字符  <br/> |两位数的操作日。  <br/> |
| `hh` <br/> |2 个字符  <br/> |此操作的两位数小时。  <br/> |
| `mm` <br/> |2 个字符  <br/> |此操作的两位数分钟数。  <br/> |
| `ss` <br/> |2 个字符  <br/> |此操作的两位数秒。  <br/> |
| `uuu…` <br/> |可变长度  <br/> |邮件的编码 UID。  <br/> |

<a name="OL15Con_AuxRef_ParsingMsgsHistory_Example"> </a>

## <a name="example"></a>示例

图 1 显示了一个 BLOB 示例，该 BLOB 表示 POP 帐户的邮件下载历史记录。 
  
**图 1.POP3 帐户的邮件下载历史记录的示例 BLOB 结构**

![用于 POP3 帐户的消息下载历史记录的 BLOB](media/OL15Con_AuxRef_ParsingMsgsHistory_Blob.gif)
  
根据表 1 和表 2 中所述的结构，此 BLOB 表示 23 封电子邮件的下载历史记录。
  
若要分析每个资源标记中的原始 UID，请注意 UID 遵循此编码：UID 中的字符大部分都是字母数字字符，并且每个非字母数字字符前面都有 ASCII 字符"$" (0x24) 。 因此，ASCII 字符 $2d 表示非字母数字字符"-"。 图 2 显示了一个示例，首先将资源标记 1 中的原始 UID 转换为 ASCII 表示形式，然后转换前面有"$"的任何非字母数字字符以生成实际的 UID：
  
`0BC535DB-EA63-11E1-A75C-00215AD7BB74`
  
**图 2.将资源标记中的原始 UID 转换为实际的消息 UID**

![将 BLOB 中的原始 UID 转换为实际消息 UID](media/OL15Con_AuxRef_ParsingMsgsHistory_BlobRscTag.gif)
  
要解释此 BLOB 中的资源标记 1：在  `0BC535DB-EA63-11E1-A75C-00215AD7BB74` 2012 年 9 月 6 日 13：11：38 成功检索具有 UID 的邮件。 
  
同样，您可以分析该 BLOB 的剩余 22 个资源标记。
  
## <a name="see-also"></a>另请参阅
<a name="OL15Con_AuxRef_ParsingMsgsHistory_AdditionalRsc"> </a>

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md)    
- [查找一个 POP3 帐户的消息下载历史记录](locating-the-message-download-history-for-a-pop3-account.md)    
- [分析 POP3 UIDL 历史记录](https://blogs.msdn.com/b/stephen_griffin/archive/2012/12/04/parsing-the-pop3-uidl-history.aspx)
    

