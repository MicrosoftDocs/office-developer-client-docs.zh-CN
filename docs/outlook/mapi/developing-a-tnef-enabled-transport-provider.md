---
title: 开发已启用 TNEF 的传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7525eee1-4016-49b8-9509-5ebbe1db819f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9f80feecda219e3bcebbf8ceb346b5034e821470
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774784"
---
# <a name="developing-a-tnef-enabled-transport-provider"></a>开发已启用 TNEF 的传输提供程序

  
  
**适用于**： Outlook 
  
提升支持不同的 MAPI 功能集的邮件系统之间的互操作性，MAPI 时，可提供传输中性封装格式 (TNEF) 作为传输数据的标准方法。 此格式封装不支持二进制流传输提供程序将其发送时可并显示消息传输到基础的消息系统的 MAPI 属性。 接收的消息的传输提供程序然后可以对要检索的原始邮件的所有属性并使其可供客户端应用程序的二进制流进行解码。 TNEF 的操作模型是：
  
- 消息客户端提交和接收平常一样 TNEF 传输邮件。
    
- 传输将传出邮件的属性分为两个类别： 基础的消息系统支持和不。 支持的基础邮件系统的属性的值转换为所需的格式。
    
- 传输使用 MAPI TNEF 方法编码到单个数据流的任何不受支持的属性。 传输然后打开该数据流成一个特殊的附件发送邮件前使用基础邮件系统的附件模型对传出邮件。
    
- 接收此类消息 TNEF 启用传输执行两项操作。 首先，它将翻译传入消息的属性 — 基础的消息系统支持的那些 — 到 MAPI 属性。 其次，如果存在此参数的特殊的附件，它使用 MAPI TNEF 方法从附件之前邮件传递到客户端应用程序检索其他 MAPI 属性。
    
使用 TNEF 对象时，MAPI 提供**ITnef**接口以供 MAPI 传输提供程序的实现。 [OpenTnefStreamEx](opentnefstreamex.md)函数用于创建 TNEF 对象并将它们与一条消息。 TNEF 流基础之上的 OLE **IStream**接口 
  
> [!NOTE]
> 您可以使用**OpenTnefStreamEx**创建 TNEF 对象。 旧**OpenTnefStream**函数仍然存在与旧的源代码的兼容性，并且不应使用任何新。 
  
**ITnef**接口提供下列方法： 
  
- [AddProps](itnef-addprops.md)
    
- [EncodeRecips](itnef-encoderecips.md)
    
- [ExtractProps](itnef-extractprops.md)
    
- [Finish](itnef-finish.md)
    
- [FinishComponent](itnef-finishcomponent.md)
    
- [OpenTaggedBody](itnef-opentaggedbody.md)
    
- [SetProps](itnef-setprops.md)
    
MAPI TNEF 实施模型支持：
  
- 而不影响其他邮件属性的所有 MAPI 属性。 为了使忞眦通过消息系统传输的 MAPI 邮件，必须封装无法编码为消息系统的属性的所有属性。 封装方案因为几乎从不已知 MAPI 兼容的客户端会收到消息发送邮件时，允许传输提供程序进行编码仅在邮件系统不这些 MAPI 邮件属性本身支持。 这意味着不"透明"不基于 MAPI，如基于 SMTP UNIX 的消息系统使用 TNEF 邮件消息系统。 这些系统接收它们支持在任何方式是典型的作为编码的 TNEF 数据流接收其，和其他属性的属性。 TNEF 传输提供程序负责为区分这两组的属性和支持的一组发送邮件系统的适当的方式。 TNEF 进行无假设来对的消息系统提供的支持级别。 但是，在包含本节中的 TNEF 用法的示例中，假定都由邮件系统支持除了邮件至少一个单独的附件。 在某些情况下，附件可以仅支持通过 uuencoded 流和传输消息文本的一部分。 仅在极少数情况下将在邮件系统具有因此很少支持邮件属性的所有属性的完整 TNEF 编码必要。
    
- 一种机制，确定是否对传入邮件 TNEF 流属于邮件，基于 MAPI 属性**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md))。 此属性应在 TNEF 流和相应的邮件头中找到。 如果属性在两个位置，有相同的值，或者缺少处于任一位置，则假定 TNEF 流属于邮件。 否则，将忽略 TNEF 流。 TNEF 启用传输负责选择对出站邮件此属性的值和相应的邮件头中对其进行编码 (例如，消息 ID: SMTP 邮件的标头) 和 TNEF 流中。
    

