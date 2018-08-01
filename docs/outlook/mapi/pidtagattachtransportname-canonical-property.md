---
title: PidTagAttachTransportName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachTransportName
api_type:
- HeaderDef
ms.assetid: 701fca52-0f96-4019-80cd-c0ccd059ff9b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6828a6436946de27020fa1177223955e07a08faf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777376"
---
# <a name="pidtagattachtransportname-canonical-property"></a>PidTagAttachTransportName 规范属性

  
  
**适用于**： Outlook 
  
包含的修改，以便它可以与 TNEF 邮件相关联的附件文件的名称。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_TRANSPORT_NAME，PR_ATTACH_TRANSPORT_NAME_A，PR_ATTACH_TRANSPORT_NAME_W  <br/> |
|标识符：  <br/> |0x370C  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>说明

TNEF 和传输提供程序使用这些属性。 他们通常是不供客户端应用程序。 
  
通常由 TNEF 使用这些属性，当基础消息系统不支持提供的文件名。 例如，它们用于当用户附加具有相同名称，例如名为配置的五个文件的多个文件。系统。 传输提供程序必须修改以确保它们都是唯一的名称。 每个已修改的名称显示在其附件**PR_ATTACH_TRANSPORT_NAME**和关联的属性。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
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

