---
title: 分析 POP3 帐户的邮件下载历史记录
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 394e1430-04d6-4d61-be13-eb695309fa73
description: 本主题介绍 POP3 BLOB 值，该值代表 POP3 帐户，以确定已下载或删除该帐户的消息的消息下载历史记录的结构。
ms.openlocfilehash: ffed3178e4e8b45f17fc335575a7febd77d40902
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774418"
---
# <a name="parsing-the-message-download-history-for-a-pop3-account"></a>分析 POP3 帐户的邮件下载历史记录

本主题介绍 POP3 BLOB 值，该值代表 POP3 帐户，以确定已下载或删除该帐户的消息的消息下载历史记录的结构。

<a name="OL15Con_AuxRef_ParsingMsgsHistory_WhyParseHistory"> </a>

## <a name="why-parse-the-message-download-history"></a>为什么解析的消息下载历史记录？

Outlook 邮局协议 (POP) 提供程序允许用户检索并在其本地设备上的新电子邮件下载并随后保留或删除这些邮件服务器上的电子邮件。 当邮件客户端检查新邮件，若要下载时，它具有能够识别和仅下载新邮件的收件箱。 邮件客户端第一个使用 UIDL （唯一 ID 列出） 命令获取以往任何时候都已传递给为唯一标识符 (UID) 的收件箱每封邮件的地图来达到此目的。 客户端还获取的已下载或删除该客户端上的收件箱邮件的消息下载历史记录。 使用邮件 UID 地图和下载历史记录，客户端可以然后确定存在这些邮件从历史记录，通过新建，因此，应下载。
  
若要获取的收件箱邮件下载历史记录：
  
- 按照中[查找邮件下载历史记录 POP3 帐户](locating-the-message-download-history-for-a-pop3-account.md)以查找[PidTagAttachDataBinary](http://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx)属性，其中包含代表 POP3 帐户的消息历史记录二进制大型对象 (BLOB) 的步骤。 
    
- 阅读本主题，其中介绍 BLOB 的结构，并显示了示例标识的已下载或删除的 POP3 帐户的收件箱邮件的 BLOB。

<a name="OL15Con_AuxRef_ParsingMsgsHistory_BLOBStructure"> </a>

## <a name="pop-blob-structure"></a>POP BLOB 结构

POP BLOB 结构，如表 1 中所述开头**版本**和**计数**后, 跟**计数**大量资源标记，其中每个以 null 结尾的两个字段。 
  
**表 1。结构 BLOB 表示消息下载历史记录的 POP3 帐户**

|**BLOB 中的字段**|**Size**|**说明**|
|:-----|:-----|:-----|
|**版本** <br/> |2 个字节  <br/> |必须为 3 (**PBLOB_VERSION_NUM**)。  <br/> |
|**Count** <br/> |2 个字节  <br/> |在此 BLOB 标记的资源的数目。  <br/> |
|资源标记  <br/> |变量  <br/> |编码的资源标记的 0 或更多 null 结尾 utf-8 字符串。 空结尾字符串数必须匹配**计数**。  <br/> |
   
每个资源标记指定应用到邮件中，有关操作，某些日期时间元数据并将编码的邮件 UID 的操作。 资源标记字符串的格式，如下所示，细分和进一步说明表 2 中。 
  
`Ocyyyymmddhhmmssuuu...`
  
**表 2。资源标记的结构**

|**资源标记中的字段**|**Size**|**说明**|
|:-----|:-----|:-----|
| `O` <br/> |1 个字符  <br/> |在电子邮件上执行操作。 值必须是"+"、"-"，或"&amp;"，分别表示成功 get、 删除或 get 删除操作。  <br/> |
| `c` <br/> |1 个字符  <br/> |消息内容操作中所涉及的一部分。 值必须是""，"h"或"b"，指示的任何内容，标头或正文，分别。  <br/> |
| `yyyy` <br/> |4 个字符  <br/> |操作四位数年份。  <br/> |
| `MM` <br/> |2 个字符  <br/> |操作的两位数表示的月份。  <br/> |
| `dd` <br/> |2 个字符  <br/> |操作的两位数的天数。  <br/> |
| `hh` <br/> |2 个字符  <br/> |操作的两位数小时数。  <br/> |
| `mm` <br/> |2 个字符  <br/> |操作的两位数分钟。  <br/> |
| `ss` <br/> |2 个字符  <br/> |操作的两位数秒钟。  <br/> |
| `uuu…` <br/> |可变长度  <br/> |邮件编码的 UID。  <br/> |

<a name="OL15Con_AuxRef_ParsingMsgsHistory_Example"> </a>

## <a name="example"></a>示例

图 1 显示值，该值代表 POP 帐户的消息下载历史记录的 BLOB 的示例。 
  
**图 1。将 BLOB 结构示例邮件下载历史记录的 POP3 帐户**

![用于 POP3 帐户的消息下载历史记录的 BLOB](media/OL15Con_AuxRef_ParsingMsgsHistory_Blob.gif)
  
基于表 1 和表 2 中所述的结构，此 BLOB 表示 23 电子邮件下载历史的记录。
  
若要分析的原始 UID 每个资源标记中，注意 UID 遵循此编码： UID 中的字符都是主要字母数字字符，并且每个非字母数字字符前面加 ASCII 字符"$"(0x24)。 以便 ASCII 字符 $2d 表示非字母数字字符"-"。 图 2 显示了示例首先将资源标记 1 中的原始 UID 转换为 ASCII 表示形式，然后将"$"若要生成的实际 UID 前面有任何非字母数字字符转换：
  
`0BC535DB-EA63-11E1-A75C-00215AD7BB74`
  
**图 2。将资源标记中的原始 UID 转换为实际邮件 UID**

![将 BLOB 中的原始 UID 转换为实际消息 UID](media/OL15Con_AuxRef_ParsingMsgsHistory_BlobRscTag.gif)
  
解释此 BLOB 中的资源标记 1： 具有 UID 消息`0BC535DB-EA63-11E1-A75C-00215AD7BB74`已成功检索在 2012 年 9 月 6 日，在 13:11:38。 
  
同样，您可以为该 BLOB 分析的其余 22 资源标记。
  
## <a name="see-also"></a>另请参阅
<a name="OL15Con_AuxRef_ParsingMsgsHistory_AdditionalRsc"> </a>

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md)    
- [查找一个 POP3 帐户的消息下载历史记录](locating-the-message-download-history-for-a-pop3-account.md)    
- [分析 POP3 UIDL 历史记录](http://blogs.msdn.com/b/stephen_griffin/archive/2012/12/04/parsing-the-pop3-uidl-history.aspx)
    

