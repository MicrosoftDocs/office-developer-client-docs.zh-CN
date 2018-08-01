---
title: TNEF 标记的邮件文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8c65339e-240c-412d-9b71-69c746468bfb
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bedfc0457b0de8287a4e7bc8bdf8fb57404e4fa8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778985"
---
# <a name="tnef-tagged-message-text"></a>TNEF 标记的邮件文本

  
  
**适用于**： Outlook 
  
已标记的消息文本使用 TNEF 解析父邮件中的附件位置。 这是通过附件的位置的消息文本中添加占位符。 此占位符或附件标记介绍一种 TNEF 知道如何解决附件和其位置的方法中的附件。 标记的格式，如下所示：
  
 `[[ <Object Title> : <KeyNum> in <Stream Name> ]] [[ <File Name> : <KeyNum> in <Transport Name> ]]`
  
 **\<对象标题\>** 和**\<文件名\>** 是包含来自本身的附件的值的变量。 在这些值不可用的情况下，通过 TNEF 附件类型基于默认标题。 
  
** \<KeyNum\>** 变量包含的文本表示形式 TNEF 由分配给附件的附件键。 基本项的值被传递到[OpenTnefStreamEx](opentnefstreamex.md)呼叫。 基本的值必须不为零，不应**OpenTnefStreamEx**每次调用相同。 它应该就足够了，使用基于从运行时库提供，任何随机数字生成器系统时间，只要您能保证他们从不零伪随机数。
  
**\<传输名称\>** 变量包含流名称传递到[OpenTnefStreamEx](opentnefstreamex.md)呼叫或**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性的值。
  
> [!NOTE]
> **PR_ATTACH_TRANSPORT_NAME**属性和**\<传输名称\>** 变量消息文本标记中的没有要进行处理要实现传输提供程序的名称。 这些项表示传输提供程序和邮件系统的附件的名称。 
  
传输提供程序通过调用[ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法要求已标记的消息文本时标记消息文本。 从已标记的文本流读取时, TNEF 替换为已具有适当的标记提供**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性中的索引处的消息文本中的单个字符。 写入标记的文本流时, TNEF 检查传入数据标记、 查找关联的附件，并标记替换为单个空格字符。
  
请注意，通过使用已标记的消息文本，传输提供程序可以保留位置所做的消息文本的消息系统的大多数更改附件。
  

