---
title: 开发启用了 TNEF 的传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7525eee1-4016-49b8-9509-5ebbe1db819f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 282b1866699b695c647caedd130ce5abc1bcbc2c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316693"
---
# <a name="developing-a-tnef-enabled-transport-provider"></a>开发启用了 TNEF 的传输提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为了提高支持不同 MAPI 功能集的邮件系统之间的互操作性, MAPI 提供了传输中性封装格式 (TNEF) 作为传输数据的标准方法。 此格式将基础邮件系统不支持的 MAPI 属性封装为二进制流, 在传输提供程序发送该流时, 可以与邮件一起传输。 接收邮件的传输提供程序随后可对二进制流进行解码, 以检索原始邮件的所有属性, 并使其可用于客户端应用程序。 TNEF 的操作模型为:
  
- 邮件客户端将邮件以正常方式提交和接收到 TNEF 传输。
    
- 传输将传出邮件的属性分为两类: 基础邮件系统所支持的类别以及不支持的邮件。 基础邮件系统支持的属性值将转换为所需的格式。
    
- 传输使用 MAPI TNEF 方法将任何不受支持的属性编码为单个数据流。 然后, 传输将该数据流转换为传出邮件的特殊附件 (使用基础邮件系统的附件模型), 然后再发送邮件。
    
- 接收此类邮件的 TNEF 启用的传输将执行两项操作。 首先, 它会将传入邮件的属性 (基础邮件系统支持的属性) 转换为 MAPI 属性。 其次, 如果存在特殊附件, 则在将邮件传递给客户端应用程序之前, 它使用 MAPI TNEF 方法从附件中检索其他 MAPI 属性。
    
mapi 提供了在使用 TNEF 对象时供 MAPI 传输提供程序使用的**ITnef**接口的实现。 [OpenTnefStreamEx](opentnefstreamex.md)函数用于创建 TNEF 对象, 并将其与邮件相关联。 TNEF 流建立在 OLE **IStream**接口的基础之上 
  
> [!NOTE]
> 您可以使用**OpenTnefStreamEx**创建 TNEF 对象。 旧的**OpenTnefStream**函数仍然存在, 可与旧源代码兼容, 不应在任何新的内容中使用。 
  
**ITnef**接口提供以下方法: 
  
- [AddProps](itnef-addprops.md)
    
- [EncodeRecips](itnef-encoderecips.md)
    
- [ExtractProps](itnef-extractprops.md)
    
- [Finish](itnef-finish.md)
    
- [FinishComponent](itnef-finishcomponent.md)
    
- [OpenTaggedBody](itnef-opentaggedbody.md)
    
- [SetProps](itnef-setprops.md)
    
MAPI TNEF 实现模型支持:
  
- 所有 MAPI 属性, 而不影响其他邮件属性。 为了使 MAPI 邮件在邮件系统中传输正常, 必须封装所有无法编码为邮件系统属性的属性。 由于在发送邮件时, 无论是否符合 MAPI 兼容的客户端将接收邮件, 封装方案都将允许传输提供程序仅对那些邮件系统不包含的 MAPI 邮件属性进行编码。本身支持。 这意味着, 使用 TNEF 的邮件不是基于 MAPI 的邮件系统 (如基于 SMTP 的 UNIX 邮件系统) 的 "不透明"。 这些系统接收它们支持的属性的方式通常为它们所支持的属性, 而其他属性则作为编码的 TNEF 数据流接收。 TNEF 传输提供程序负责区分这两组属性, 并以正确的方式为邮件系统发送受支持的集。 TNEF 对邮件系统提供的支持级别没有任何假设。 但是, 在此部分中包括的 TNEF 用法示例中, 假定邮件系统至少支持一个与邮件旁边的单个附件。 在某些情况下, 仅可通过 uuencoded 流支持附件, 并作为邮件文本的一部分进行传输。 仅在极少数情况下, 邮件系统对邮件属性的支持非常少, 对所有属性的完全 TNEF 编码都是必需的。
    
- 一种机制, 用于根据 MAPI 属性**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 确定传入邮件上的 TNEF 流是否属于邮件。 应在 TNEF 流中和适当的邮件头中找到此属性。 如果该属性在两个位置都具有相同的值, 或者在这两个位置中都缺少该属性, 则认为 TNEF 流属于该邮件。 否则, TNEF 流将被忽略。 启用 TNEF 的传输负责在出站邮件上选择此属性的值, 并在适当的邮件头 (例如, SMTP 邮件的邮件 ID: 头) 和 TNEF 流中对其进行编码。
    

