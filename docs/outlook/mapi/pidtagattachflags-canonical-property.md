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
ms.openlocfilehash: efccd75cce04e4e392a7fbd9feecc7c8b49ab57e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339331"
---
# <a name="pidtagattachflags-canonical-property"></a>PidTagAttachFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含附件的标志的位掩码。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_FLAGS  <br/> |
|标识符:  <br/> |0x3714  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

此属性用于 MHTML 支持。 
  
可以为**PR_ATTACH_FLAGS**位掩码设置以下一个或多个标志: 
  
ATT_INVISIBLE_IN_HTML 
  
> 指示此附件对 HTML 呈现应用程序不可用, 应在多用途 Internet 邮件扩展 (MIME) 处理中被忽略。 
    
ATT_INVISIBLE_IN_RTF 
  
> 指示此附件不适用于以 rtf 格式呈现的应用程序, 并且应由 MAPI 忽略。
    
如果**PR_ATTACH_FLAGS**属性为零或不存在, 则附件将由所有应用程序处理。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

