---
title: PidTagHasAttachments 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagHasAttachments
api_type:
- HeaderDef
ms.assetid: fd236d74-2868-46a8-bb3d-17f8365931b6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b618e5a79c3b7e3810ea541aa9b905dfa4188a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777669"
---
# <a name="pidtaghasattachments-canonical-property"></a>PidTagHasAttachments 规范属性

  
  
**适用于**： Outlook 
  
如果邮件包含至少一个附件，包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_HASATTACH  <br/> |
|标识符：  <br/> |0x0E1B  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>说明

消息存储从**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性的**MSGFLAG_HASATTACH**标志复制此属性。 然后，客户端应用程序可以使用**PR_HASATTACH**排序所依据邮件查看器中的邮件附件。 
  
使用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法都会更新此属性的值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
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

