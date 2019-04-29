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
  
若要接收自定义附件处理的 TNEF 邮件, 请执行以下操作:
  
1. 将传入邮件中的所有传输属性 (邮件系统支持的属性) 从传入邮件导入到新 MAPI 邮件中。 这包括包含 TNEF 数据流的邮件文本。
    
2. 标识和解码包含 TNEF 流的特殊附件。
    
3. 将传入邮件中的所有附件提取到新 mapi 邮件的 mapi 附件中。 已恢复的文件名或附件上的其他标识标记应放入新附件的**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性中, 以便[ITnef:: ExtractProps](itnef-extractprops.md)方法以后可以将正确的附件与在邮件文本中编码的附件标记相关联。 
    
4. 创建 OLE **IStream**接口以回绕解码的 TNEF 流, 并在调用[OpenTnefStreamEx](opentnefstreamex.md)函数的同时将该对象与新 MAPI 邮件一起使用。 
    
5. 调用**ITnef:: ExtractProps**方法, 从 TNEF 数据流恢复邮件的 nontransmittable 属性。 
    
6. 使用 MAPI_CREATE 和 MAPI_MODIFY 标志集调用[ITnef:: OpenTaggedBody](itnef-opentaggedbody.md)方法。 此调用将从邮件文本中删除附件标记, 并将其转换为 MAPI 邮件中的附件位置信息。 
    
7. 通过 MAPI 后台处理程序传递邮件。
    

