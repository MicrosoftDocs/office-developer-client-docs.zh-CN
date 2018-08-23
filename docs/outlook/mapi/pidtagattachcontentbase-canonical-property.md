---
title: PidTagAttachContentBase 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachContentBase
api_type:
- HeaderDef
ms.assetid: 35c10264-6998-4c46-8cef-82708c96d9c7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 40e2efbf512265dffeee43d09e85879e8c3a0e56
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582418"
---
# <a name="pidtagattachcontentbase-canonical-property"></a>PidTagAttachContentBase 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含多用途 Internet 邮件扩展 (MIME) 邮件附件的内容的基本标头。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_CONTENT_BASE，PR_ATTACH_CONTENT_BASE_A，PR_ATTACH_CONTENT_BASE_W  <br/> |
|标识符：  <br/> |0x3711  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

使用这些属性 MHTML 支持。 它们表示的适当的 MIME 正文部分内容的基本标头。 
  
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

