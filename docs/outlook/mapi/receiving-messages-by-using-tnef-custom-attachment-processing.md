---
title: 使用 TNEF 自定义附件处理接收邮件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb5082fa-8fe3-46fe-b2de-b6dd1af79ea7
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 046b537d41b318fa857ef77f1906edcf2c3aa2bf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429318"
---
# <a name="receiving-messages-by-using-tnef-custom-attachment-processing"></a>使用 TNEF 自定义附件处理接收邮件

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要接收包含自定义附件处理的 TNEF 邮件：：
  
1. 将传入邮件中所有可传输的属性（邮件系统支持的属性）导入到新的 MAPI 邮件中。 这包括消息文本，其中包含 TNEF 数据流。
    
2. 标识并解码包含 TNEF 流的特殊附件。
    
3. 将传入邮件的所有附件提取到新 MAPI 邮件上的 MAPI 附件中。 恢复的文件名或附件上的其他标识标记应放在新附件的 **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性中，以便 [ITnef：：ExtractProps](itnef-extractprops.md) 方法稍后可以将正确的附件与邮件文本中编码的附件标记关联。 
    
4. 创建 OLE **IStream** 接口以环绕解码的 TNEF 流，在 [调用 OpenTnefStreamEx](opentnefstreamex.md) 函数时将该对象与新的 MAPI 消息一同使用。 
    
5. 调用 **ITnef：：ExtractProps** 方法从 TNEF 数据流恢复邮件的不可传输属性。 
    
6. 调用 [ITnef：：OpenTaggedBody](itnef-opentaggedbody.md) 方法，MAPI_CREATE和MAPI_MODIFY标记。 此调用从邮件文本中删除附件标记，并将其转换为 MAPI 邮件中的附件位置信息。 
    
7. 通过 MAPI 后台处理程序传递邮件。
    

