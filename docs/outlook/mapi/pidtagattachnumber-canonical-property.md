---
title: PidTagAttachNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachNumber
api_type:
- HeaderDef
ms.assetid: 507e0f2c-383c-4e2f-917b-159913f7234d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f6de157864bff5be41b6e030d555be7b60dcda5e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594752"
---
# <a name="pidtagattachnumber-canonical-property"></a>PidTagAttachNumber 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含唯一标识其父消息中的附件数。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_NUM  <br/> |
|标识符：  <br/> |0x0E21  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

消息存储生成和维护此属性。 附件数是次要排序关键字后的呈现位置，以对附件表。 
  
 **PR_ATTACH_NUM**用于与[IMessage::OpenAttach](imessage-openattach.md)方法打开附件。 客户端应用程序的会话中的邮件附件的**PR_ATTACH_NUM**属性保持不变，只要附件表处于打开状态。 
  
消息存储将更改传播到使用**IMessage::CreateAttach**和**IMessage::DeleteAttach**方法的表。 自行选择消息存储可以生成对打开附件表的表通知，以便客户端可以重新同步到这些更改。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

