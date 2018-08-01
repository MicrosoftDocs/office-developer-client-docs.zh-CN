---
title: 邮件文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d1837f1-494f-481b-9e09-ab8249f1488c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9dba148646678f0740c5b2c338ae345ecd76dfac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776508"
---
# <a name="message-text"></a>邮件文本

  
  
**适用于**： Outlook 
  
对于在 MIME 模式下的出站邮件，内容类型取决于是否有附件和消息文本的外观。 如果有附件，内容类型是_多部分/混合;_ 消息文本，每个附件成为单独消息内容，每个都有其自己的内容类型的部分。 如果不有任何附件，消息的内容类型为_text/plain_并且没有只有一个部件。 
  
消息文本不会行-包装除非一些行超出 140 个字符的长度。 如果包含空格，在整个文本换到 76 列和_用引号括起来打印_编码用于保留换行符。 内容类型取决于，如下所示在消息文本中，找到哪些字符： 
  
- 如果只找到 7 位字符，并且没有行超过 140 个字符的长度，消息将为 ASCII 文本。 _Content-type: text/plain; charset = 我们 ascii_(内容传送编码 = 假定 7 位。) 
    
- 如果找到较长的行或 8 位字符，邮件文本及字符集由区域设置。 从由 ISO 标准 8859 定义的字符集，应选择它。 _Content-type: text/plain; charset = iso-8859-1_（或其他有效字符集） 
    
     _Content-Transfer-Encoding: quoted-printable_
    
入站 MIME 邮件，如果第一条消息内容部件具有_内容类型： 文本 /\* _ （即，任何文本类型） 和识别其字符集，它被映射到**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))。 不满足此条件的第一个邮件内容部件将成为附件。 任何后续部分还将变成附件。
  
在 uuencode 模式下，出站邮件中的消息文本是折行 78 列，与 MS Mail 3.x。 内容类型为"text/plain。" 若要保留原始消息的分段符在这些情况下，观察换行文本中的以下约定。 有三个结束一行文本，每个都有其自己的字符序列的可能原因：
  
- 换行符。 原始文本包含新行输入的用户 （段落标记）。 在传输，这将映射到换行符不带上述空格。 如果用户输入新行前面由空格，则应去除空值。
    
- 行 nobreak。 原始文本包含太长，以适应单行邮件上的单词。 在传输，这将映射到新行前面两个空值。
    
- 换行。 原始文本包含任何换行符、 文本是太长，可根据单行邮件，但可以是两个字词之间断开。 在传输，这将映射到新行前面有一个空格。
    

