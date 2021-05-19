---
title: TNEF-Tagged消息文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8c65339e-240c-412d-9b71-69c746468bfb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2b4d4cd790870a024cac6f2ed9952d18a970235a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419917"
---
# <a name="tnef-tagged-message-text"></a>TNEF-Tagged消息文本

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
TNEF 使用带标记的邮件文本解析父邮件中的附件位置。 为此，在附件位置的邮件文本中添加位置持有者。 此位置持有者（或 attachment 标记）以 TNEF 知道如何解析附件及其位置的方式描述附件。 标记的格式如下所示：
  
 `[[ <Object Title> : <KeyNum> in <Stream Name> ]] [[ <File Name> : <KeyNum> in <Transport Name> ]]`
  
 **\< 对象标题 \>****\< 和文件名 \>** 是包含从附件本身获得的值的变量。 如果这些值不可用，则 TNEF 根据附件类型默认使用标题。 
  
**\< KeyNum \>** 变量包含 TNEF 分配给附件的附件键的文本表示形式。 键的基值将传递到 [OpenTnefStreamEx](opentnefstreamex.md) 调用中。 基值不能为零，并且对于每次调用 **OpenTnefStreamEx** 时不应相同。 根据系统时间从运行时库提供的随机数字生成器使用伪随机数字就足够了，只要你保证它们从不为零。
  
Transport **\< Name \>** 变量包含传入 [OpenTnefStreamEx](opentnefstreamex.md)调用的流名称或 **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性的值。
  
> [!NOTE]
> the **PR_ATTACH_TRANSPORT_NAME** property and the **\< Transport Name \>** variable in a message text tag have nothing to do with the name of the transport provider you are implementing. 这些项目表示传输提供程序和邮件系统的附件的名称。 
  
当传输提供程序通过调用 [ITnef：：OpenTaggedBody](itnef-opentaggedbody.md) 方法请求标记的邮件文本时，邮件文本将被标记。 从带标记的文本流中读取时，TNEF 将 PR_RENDERING_POSITION ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md) **)** 属性中提供索引的消息文本中的单个字符替换为相应的标记。 当写入带标记的文本流时，TNEF 会检查传入的标记数据，查找关联的附件，并用单个空格字符替换标记。
  
请注意，通过使用带标记的邮件文本，传输提供程序可以保留附件的定位，而不管邮件系统对邮件文本进行了何种更改。
  

