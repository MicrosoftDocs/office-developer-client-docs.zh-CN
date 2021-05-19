---
title: 消息文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d1837f1-494f-481b-9e09-ab8249f1488c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fcbdec5adcb47ffac431a832cbb851ee4ebe16d8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418545"
---
# <a name="message-text"></a>消息文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对于 MIME 模式下的出站邮件，内容类型取决于是否有附件以及邮件文本的外观。 如果存在附件，则 Content 类型为  _multipart/mixed;_ 邮件文本和每个附件将成为邮件内容的单独部分，每个附件都有自己的内容类型。 如果没有附件，则邮件的内容类型为  _文本/纯_ 文本，并且只有一部分。 
  
邮件文本不换行，除非某些行的长度超过 140 个字符。 如果包含，则整个文本将换行为 76 列，并且  _使用 quoted-printable_ 编码来保留换行符。 内容类型取决于在邮件文本中发现的字符，如下所示： 
  
- 如果只找到 7 位字符且行长度不超过 140 个字符，则消息为 ASCII 文本。 _Content-type：text/plain;charset=us-ascii_ (Content-Transfer-Encoding=7bit。)  
    
- 如果找到长行或 8 位字符，则消息为文本，字符集由区域设置确定。 应从 ISO 标准 8859 定义的字符集选择它。 _Content-type： text/plain; charset=iso-8859-1_ (or another valid charset)  
    
     _Content-Transfer-Encoding: quoted-printable_
    
对于入站 MIME 邮件，如果第一个邮件内容部分具有 _Content-type： text/ \*_ (，即识别任何文本类型) 且其字符集已被识别，它将映射到 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 。 第一个不满足此条件的邮件内容部件将成为附件。 任何后续部分也成为附件。
  
在 uuencode 模式下，出站邮件中的邮件文本换行为 78 列，而 MS Mail 3.x 则换行。 content-type 为"text/plain"。 若要在这些情况下保留原始邮件的段落换行符，请遵循封装文本中的以下约定。 结束一行文本有三种可能的原因，每个文本都有其自己的字符序列：
  
- 换行符。 原始文本包含用户在段落标记 (输入的) 。 在传输中，这会映射到没有前面的空值的新行。 如果用户在空行的前面输入了一条新行，应去除空白。
    
- 换行符。 原始文本包含的单词太长，无法容纳在邮件的一行上。 在传输中，这会映射到前面有两个空白的新行。
    
- 换行。 原始文本未包含换行符，文本太长，无法容纳在邮件的一行上，但可以在两个单词之间断开。 在传输中，这会映射到前面有一个空白的新行。
    

