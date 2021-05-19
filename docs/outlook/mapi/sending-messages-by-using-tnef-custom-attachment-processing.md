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
  
在发送邮件时自定义附件处理：
  
1. 通过向 [OpenTnefStreamEx](opentnefstreamex.md)函数传递 **IStream** 接口和消息来获取 TNEF 对象。 
    
2. 通过调用 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法获取邮件的所有已定义属性的列表。 
    
3. 使用 [IMAPIProp](imapipropiunknown.md) 方法排除邮件系统支持的所有属性。 在适当时，以邮件系统所需的格式将这些属性写入邮件系统。 
    
4. 调用 [ITnef：：AddProps](itnef-addprops.md) 方法，通过设置"附件"标记，仅添加邮件上的属性（即，附件TNEF_PROP_MESSAGE_ONLY属性）。 
    
5. 使用以下项目调用 [ITnef：：AddProps：TNEF_PROP_EXCLUDE](itnef-addprops.md) 标志、包含 **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 或 **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性的属性标记数组，以及指定要处理的附件的附件标识符。
    
6. 使用 [ITnef：：SetProps](itnef-setprops.md) 方法添加具有唯一字符串的 **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性标记，该字符串标识邮件系统的附件（如果附件具有邮件系统不支持的文件名）。 例如，具有同一原始文件名的多个附件，或不是邮件系统的有效文件名的文件名。 在带标记的邮件文本中写入附件标记以将附件与数据关联时，此字符串将和键号一起使用。 有关详细信息，请参阅 [TNEF 标记的邮件文本](tnef-tagged-message-text.md)。
    
7. 对每个 **附件重复 AddProps** 和 **SetProps** 调用。 
    
8. 在添加 [所有请求的属性后，调用 ITnef：：Finish](itnef-finish.md) 方法将邮件编码到 TNEF 流中。 
    
9. 通过调用 [ITnef：：OpenTaggedBody](itnef-opentaggedbody.md) 方法获取带标记的邮件文本。 此标记文本使用 **IStream** 接口中的方法读取，使用邮件系统的附件模型进行编码，并写入邮件系统。 
    
10. 调用 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法来释放 [ITnef](itnefiunknown.md) 对象。 
    
11. 通过邮件系统的附件模型将剩余附件写入邮件系统。
    
传输提供程序应该使用前面介绍的过程处理附件。 如果不可能，传输提供程序应执行以下步骤进行自定义附件处理：
  
1. 传输提供程序可确保所有 **PR_ATTACH_TRANSPORT_NAME** 的附件属性包含唯一值，这些值是邮件系统的有效附件标识符。 
    
2. 然后，传输提供程序将单个调用用于每个附件的 **ITnef：：AddProps，** 并传递TNEF_PROP_CONTAINED标记。 
    

