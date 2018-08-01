---
title: PidTagAttachFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachFlags
api_type:
- HeaderDef
ms.assetid: 47e01131-f399-43cb-9815-aba69638c3fb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b934f9694061e17118be35e3fabeeff3bbc61a37
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777336"
---
# <a name="pidtagattachflags-canonical-property"></a>PidTagAttachFlags 规范属性

  
  
**适用于**： Outlook 
  
包含附件的标志的位掩码。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_FLAGS  <br/> |
|标识符：  <br/> |0x3714  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>说明

此属性用于 MHTML 支持。 
  
可以为**PR_ATTACH_FLAGS**位掩码设置一个或多个以下标志： 
  
ATT_INVISIBLE_IN_HTML 
  
> 指示此附件对 HTML 呈现应用程序不可用，并且应忽略中多用途 Internet 邮件扩展 (MIME) 处理。 
    
ATT_INVISIBLE_IN_RTF 
  
> 指示此附件对呈现富文本格式 (RTF) 中的应用程序不可用，并且应忽略 MAPI。
    
如果**PR_ATTACH_FLAGS**属性为零或不存在，附件是处理的所有应用程序。 
  
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

