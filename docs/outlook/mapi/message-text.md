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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356866"
---
# <a name="message-text"></a>消息文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对于 MIME 模式下的出站邮件, 内容类型取决于是否存在附件以及邮件文本的外观。 如果存在附件, 则内容类型为_多部分/混合的;_ 邮件文本和每个附件将成为邮件内容的一个单独部分, 每个附件都有其自己的内容类型。 如果没有附件, 则邮件的内容类型为_text/纯文本_, 并且只有一个部件。 
  
除非某个行的长度超过140个字符, 否则邮件文本不会换行。 如果有, 则整个文本将被包装为76列, 可使用_带引号的可打印_编码来保留换行符。 内容类型取决于在邮件文本中找到的字符, 如下所示: 
  
- 如果仅找到7位字符, 并且没有任何行的长度超过140个字符, 则该邮件为 ASCII 文本。 _Content-type: text/普通; 字符集 = us-ascii_(假定为 "内容传输-编码 = 7bit"。) 
    
- 如果找到长行或8位字符, 则邮件为文本, 字符集由区域设置决定。 应从 ISO standard 8859 定义的字符集中选择此设置。 _Content-type: text/普通; 字符集 = iso-8859-1_(或其他有效的字符集) 
    
     _Content-Transfer-Encoding: quoted-printable_
    
对于入站 MIME 邮件, 如果第一个邮件内容部件包含_content type: text/\* _ (即任何文本类型), 并识别其字符集, 则将其映射到**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))。 未满足此条件的第一个邮件内容部件将成为附件。 任何后续部件也会变成附件。
  
在 uuencode 模式下, 出站邮件中的邮件文本被自动换行为78列, 如 MS Mail 3。 内容类型为 "text/普通"。 若要在这些情况下保留原始邮件的段落换行, 请在换行文本中遵循以下约定。 有三个可能的原因: 结束一行文本, 每个原因都有其自己的字符序列:
  
- 换行符。 原始文本包含用户输入的换行符 (段落标记)。 在传输中, 这会映射到不带前空白的换行符。 如果用户输入的前带空格的换行符, 则应去除空白。
    
- 行-nobreak。 原始文本包含的词太长, 不能在邮件的一行中显示。 在传输中, 此方法映射到前有两个空格的换行符。
    
- 换行。 原始文本不包含任何行, 文本太长, 不能在邮件的一行中显示, 但可以在两个单词之间断线。 在传输中, 这会映射到前跟一个空白的换行符。
    

