---
title: 开发TNEF-Enabled传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7525eee1-4016-49b8-9509-5ebbe1db819f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 282b1866699b695c647caedd130ce5abc1bcbc2c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439000"
---
# <a name="developing-a-tnef-enabled-transport-provider"></a>开发TNEF-Enabled传输提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为了提升支持不同 MAPI 功能集的邮件系统之间的互操作性，MAPI 提供了传输中性封装格式 (TNEF) 作为传输数据的标准方法。 此格式将不受基础邮件系统支持的 MAPI 属性封装到二进制流中，传输提供程序发送该二进制流时，可以随邮件一起传输。 然后，接收邮件的传输提供程序可以解码二进制流以检索原始邮件的所有属性，并使它们可用于客户端应用程序。 TNEF 的操作模型是：
  
- 邮件客户端正常向 TNEF 传输提交和接收邮件。
    
- 传输将传出邮件的属性分为两类：基础邮件系统支持的属性和不支持的属性。 基础邮件系统支持的属性的值将转换为所需格式。
    
- 传输使用 MAPI TNEF 方法将任何不受支持的属性编码为单个数据流。 传输随后使用基础邮件系统的附件模型，在发送邮件之前，将该数据流转换为传出邮件上的特殊附件。
    
- 接收此类邮件的启用 TNEF 的传输会做两件事。 首先，它将传入邮件的属性（基础邮件系统支持的属性）转换为 MAPI 属性。 其次，如果存在特殊附件，它将使用 MAPI TNEF 方法在将邮件传递至客户端应用程序之前从附件检索其他 MAPI 属性。
    
MAPI 提供 **ITnef 接口** 的实现，供 MAPI 传输提供程序在使用 TNEF 对象时使用。 [OpenTnefStreamEx](opentnefstreamex.md)函数用于创建 TNEF 对象并将其与消息关联。 TNEF 流构建于 OLE **IStream 接口** 的顶部 
  
> [!NOTE]
> 使用 **OpenTnefStreamEx** 创建 TNEF 对象。 旧的 **OpenTnefStream** 函数仍然存在，以与旧源代码兼容，不应用于任何新内容。 
  
**ITnef** 接口提供以下方法： 
  
- [AddProps](itnef-addprops.md)
    
- [EncodeRecips](itnef-encoderecips.md)
    
- [ExtractProps](itnef-extractprops.md)
    
- [Finish](itnef-finish.md)
    
- [FinishComponent](itnef-finishcomponent.md)
    
- [OpenTaggedBody](itnef-opentaggedbody.md)
    
- [SetProps](itnef-setprops.md)
    
MAPI TNEF 实现模型支持：
  
- 所有 MAPI 属性都不会影响其他邮件属性。 为了使 MAPI 邮件在通过邮件系统传输时能保留下来，必须封装无法编码为邮件系统属性的所有属性。 由于在发送消息时几乎永远不会知道符合 MAPI 的客户端是否将接收邮件，因此封装方案允许传输提供程序仅对邮件系统不支持的 MAPI 邮件属性进行编码。 这意味着使用 TNEF 的邮件对于不基于 MAPI 的邮件系统（如基于 SMTP 的邮件系统）UNIX不透明。 这些系统以他们典型的任何方式接收支持的属性，其他属性作为编码的 TNEF 数据流接收。 TNEF 传输提供程序负责区分这两组属性，并正确发送邮件系统支持的属性集。 TNEF 对邮件系统提供的支持级别不做任何假设。 但是，在本节包含的 TNEF 用法示例中，假定邮件系统支持邮件之外至少一个附件。 在某些情况下，附件只能通过 uuencoded 流获得支持，并作为邮件文本的一部分进行传输。 仅在极少数情况下，邮件系统才对邮件属性的支持非常少，因此需要所有属性的完整 TNEF 编码。
    
- 一种根据 MAPI 属性 **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 确定传入邮件上的 TNEF 流是否属于邮件的机制。 此属性应同时在 TNEF 流和相应的邮件头中找到。 如果属性在两处具有相同的值，或者任一位置都缺失，则假定 TNEF 流属于邮件。 否则，TNEF 流将被忽略。 启用 TNEF 的传输负责为出站邮件上的此属性选择一个值，并在适当的邮件头 (例如，SMTP 邮件的 Message-ID： 标头) 以及 TNEF 流中对该值进行编码。
    

