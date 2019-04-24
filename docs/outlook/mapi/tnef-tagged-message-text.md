---
title: TNEF 标记的邮件文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8c65339e-240c-412d-9b71-69c746468bfb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2b4d4cd790870a024cac6f2ed9952d18a970235a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339590"
---
# <a name="tnef-tagged-message-text"></a>TNEF 标记的邮件文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
TNEF 使用标记的邮件文本来解析父邮件中的附件位置。 这是通过在邮件文本中的附件位置添加占位符来实现的。 此 "放置位置" 或 "附件" 标记描述附件的方式是, TNEF 知道如何解析附件及其位置。 这些标记的格式如下所示:
  
 `[[ <Object Title> : <KeyNum> in <Stream Name> ]] [[ <File Name> : <KeyNum> in <Transport Name> ]]`
  
 ** \<对象标题\> ** **和\<文件名是包含从附件本身\> **获取的值的变量。 在这些值不可用的情况下, 标题将根据附件类型默认使用 TNEF。 
  
KeyNum 变量包含通过 TNEF 分配给附件的附件密钥的文本表示形式。 ** \<\> ** 键的基值将传递到[OpenTnefStreamEx](opentnefstreamex.md)调用中。 基值不得为零, 并且对于每个**OpenTnefStreamEx**调用都不应相同。 只要您保证它们从不为零, 就可以根据系统时间从运行时库提供的任何随机编号生成器使用伪随机数字。
  
[](opentnefstreamex.md) **\>传输名称变量包含传递到 OpenTnefStreamEx 调用中的流名称或 PR_ATTACH_TRANSPORT_NAME (PidTagAttachTransportName) 属性的\<** 值。[](pidtagattachtransportname-canonical-property.md) ****
  
> [!NOTE]
> message 文本标记中的**PR_ATTACH_TRANSPORT_NAME**属性和** \<transport NAME\> **变量与您要实现的传输提供程序的名称无任何不同之处。 这些项表示传输提供程序和邮件系统的附件的名称。 
  
当传输提供程序通过调用[ITnef:: OpenTaggedBody](itnef-opentaggedbody.md)方法来请求标记的邮件文本时, 将标记邮件文本。 从标记文本流读取时, TNEF 将**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性中提供的索引处的邮件文本中的单个字符替换为相应的标记。 在向标记文本流中写入时, TNEF 会检查标记的传入数据, 查找关联的附件, 并将标记替换为单个空格字符。
  
请注意, 通过使用带标记的邮件文本, 传输提供程序可以保留附件的位置, 而不考虑邮件系统对邮件文本所做的大多数更改。
  

