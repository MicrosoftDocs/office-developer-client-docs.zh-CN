---
title: 使用 TNEF 自定义附件处理发送邮件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: da318b6f-128a-44b5-8357-a130022030a1
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: f9d154b26319f5ed72b1abd6aeef307d07a63bda
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339695"
---
# <a name="sending-messages-by-using-tnef-custom-attachment-processing"></a>使用 TNEF 自定义附件处理发送邮件

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在发送邮件时自定义附件处理:
  
1. 通过将**IStream**接口和邮件传递到[OpenTnefStreamEx](opentnefstreamex.md)函数来获取 TNEF 对象。 
    
2. 通过调用[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法获取邮件的所有已定义属性的列表。 
    
3. 使用[IMAPIProp](imapipropiunknown.md)方法排除邮件系统支持的所有属性。 在适当的时间将这些属性以邮件系统所需的格式写入邮件系统。 
    
4. 调用[ITnef:: AddProps](itnef-addprops.md)方法以仅添加邮件的属性 (即附件的无属性), 方法是设置 TNEF_PROP_MESSAGE_ONLY 标志。 
    
5. 使用以下项调用[ITnef:: AddProps](itnef-addprops.md) : TNEF_PROP_EXCLUDE 标志、包含**PR_ATTACH_DATA_BIN**的属性标记数组 ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 或**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))属性和一个附件标识符, 用于指定要处理的附件。
    
6. 使用[ITnef:: SetProps](itnef-setprops.md)方法添加**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性标记, 其中包含标识邮件系统附件的唯一字符串 (如果附件的文件名包含邮件系统不支持。 例如, 具有相同原始文件名的多个附件, 或文件名不是邮件系统的有效文件名。 将附件标记添加到标记的邮件文本中时, 此字符串将与键号一起使用, 以将附件与其数据关联。 有关详细信息, 请参阅以[TNEF 标记的邮件文本](tnef-tagged-message-text.md)。
    
7. 对每个附件重复**AddProps**和**SetProps**调用。 
    
8. 在添加所有请求的属性后, 调用[ITnef:: Finish](itnef-finish.md)方法将邮件编码到 TNEF 流中。 
    
9. 通过调用[ITnef:: OpenTaggedBody](itnef-opentaggedbody.md)方法获取带标签的邮件文本。 此标记文本是使用**IStream**接口中的方法 (使用邮件系统的附件模型进行编码, 并将其写出到邮件系统) 进行读取的。 
    
10. 调用[IUnknown:: release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法以释放[ITnef](itnefiunknown.md)对象。 
    
11. 通过邮件系统的附件模型将其余附件写入邮件系统。
    
您的传输提供程序应使用前面介绍的过程来处理附件。 如果这是不可能的, 则传输提供商应使用以下步骤进行自定义附件处理:
  
1. 传输提供程序确保所有附件的**PR_ATTACH_TRANSPORT_NAME**属性都包含作为邮件系统的有效附件标识符的唯一值。 
    
2. 然后, 传输提供程序对每个附件使用对**ITnef:: AddProps**的单个调用, 并传入 TNEF_PROP_CONTAINED 标志。 
    

