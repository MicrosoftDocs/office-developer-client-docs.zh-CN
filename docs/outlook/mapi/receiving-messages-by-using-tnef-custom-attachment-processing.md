---
title: 使用 TNEF 自定义附件处理接收消息
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb5082fa-8fe3-46fe-b2de-b6dd1af79ea7
description: 上次修改时间： 2015 年 12 月 7 日
ms.openlocfilehash: 18fc0983554284355dcdfb301fd41a0161a860fe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778613"
---
# <a name="receiving-messages-by-using-tnef-custom-attachment-processing"></a>使用 TNEF 自定义附件处理接收消息

 
  
**适用于**： Outlook 
  
若要将收到带有自定义的附件处理的 TNEF 邮件：
  
1. 导入所有可传送的属性-邮件系统支持的那些 — 从到新的 MAPI 邮件的传入消息。 这包括消息文本，其中包含 TNEF 数据流。
    
2. 标识并解码特殊附件包含的 TNEF 流。
    
3. 到新的 MAPI 邮件上的 MAPI 附件传入邮件中提取的所有附件。 恢复的文件名或附件，其他标识标记应放置到新附件的**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性，以便的[ITnef::ExtractProps](itnef-extractprops.md)方法更高版本与编码消息文本中的附件标记关联的正确的附件。 
    
4. 创建一个 OLE **IStream**接口环绕解码 TNEF 流和[OpenTnefStreamEx](opentnefstreamex.md)函数调用中使用新的 MAPI 邮件以及该对象。 
    
5. 调用**ITnef::ExtractProps**方法从 TNEF 数据流恢复邮件 nontransmittable 属性。 
    
6. 调用 MAPI_CREATE 和 MAPI_MODIFY 设置 flags [ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法。 此呼叫从消息文本中删除附件标记，并将它们转换为附件 MAPI 消息中的位置信息。 
    
7. 通过 MAPI 后台处理程序将邮件传递。
    

