---
title: PidTagOriginalAuthorEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorEmailAddress
api_type:
- COM
ms.assetid: 67cda756-ba71-4f29-a601-55359e44d93b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1954e1760fead9cbe13f0f2394f8095cab7f26ce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777927"
---
# <a name="pidtagoriginalauthoremailaddress-canonical-property"></a>PidTagOriginalAuthorEmailAddress 规范属性

  
  
**适用于**： Outlook 
  
包含一条消息，即之前正在转发或答复邮件的第一个版本的作者的电子邮件地址。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS，PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_A，PR_ORIGINAL_AUTHOR_EMAIL_ADDRESS_W  <br/> |
|标识符：  <br/> |0x007A  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |Server  <br/> |
   
## <a name="remarks"></a>说明

这些属性是邮件的作者的地址属性的示例。 在首次提交邮件，客户端应用程序应将这些属性设置为**PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)) 属性的值。 当转发或答复邮件永远不会更改它。
  
原始作者属性允许保留来自域外部的本地消息的信息。 当邮件到达从其他邮件的域时，如从 Internet，这些属性提供一种方法，以确保原始信息不会丢失。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

