---
title: 使用 TNEF 自定义附件处理发送邮件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: da318b6f-128a-44b5-8357-a130022030a1
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: f9d154b26319f5ed72b1abd6aeef307d07a63bda
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388565"
---
# <a name="sending-messages-by-using-tnef-custom-attachment-processing"></a>使用 TNEF 自定义附件处理发送邮件

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
发送邮件时，自定义附件处理：
  
1. 通过将一个**IStream**接口和消息传递到[OpenTnefStreamEx](opentnefstreamex.md)函数获取 TNEF 对象。 
    
2. 通过调用[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法获得邮件的所有定义属性的列表。 
    
3. 使用[IMAPIProp](imapipropiunknown.md)方法来排除在邮件系统支持的所有属性。 在适当的时间将这些属性写入邮件系统中的消息的系统要求的格式。 
    
4. 调用[ITnef::AddProps](itnef-addprops.md)方法来添加对邮件仅属性 — 即，没有对附件的属性，通过设置 TNEF_PROP_MESSAGE_ONLY 标志。 
    
5. 使用这些项目调用[ITnef::AddProps](itnef-addprops.md) : TNEF_PROP_EXCLUDE 标志、 属性标记数组包含**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 或**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))属性，并指定要处理的附件的附件标识符。
    
6. 使用[ITnef::SetProps](itnef-setprops.md)方法添加**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性标记与标识邮件系统的附件，如果附件文件名的唯一字符串的无法支持邮件系统。 例如，多个附件具有相同的原始文件名或不是有效的文件名为邮件系统的文件名。 此字符串将用于与主要号码已标记的消息文本中写入的附件标记时其数据相关联的附件。 有关详细信息，请参阅[TNEF-Tagged 消息文本](tnef-tagged-message-text.md)。
    
7. 每个附件重复**AddProps**和**SetProps**呼叫。 
    
8. 调用[ITnef::Finish](itnef-finish.md)方法后所有请求的属性将被添加到 TNEF 流编码邮件。 
    
9. 通过调用[ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法来获取标记的消息文本。 从**IStream**接口，使用消息系统的附件模型编码和写出到邮件系统使用方法读取此标记的文本。 
    
10. 调用[IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法以释放[ITnef](itnefiunknown.md)对象。 
    
11. 编写邮件系统的附件模型通过在邮件系统的其余附件。
    
传输提供程序应使用过程附件前面所述的过程。 如果这是不可能的传输提供程序应进行自定义的附件处理使用以下步骤：
  
1. 传输提供程序可确保所有附件的**PR_ATTACH_TRANSPORT_NAME**属性包含唯一值都是有效的附件的邮件系统的标识符。 
    
2. 传输提供程序并将每个附件，TNEF_PROP_CONTAINED 标志中传递到**ITnef::AddProps**单个呼叫。 
    

