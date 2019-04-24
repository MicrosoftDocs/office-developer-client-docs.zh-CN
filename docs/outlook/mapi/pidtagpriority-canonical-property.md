---
title: PidTagPriority 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPriority
api_type:
- COM
ms.assetid: 0f3a628f-5f8e-4716-98cc-868bd3400ba9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b9c0f5ebeae21d6d683bbb5def727d29a34bcdb6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339429"
---
# <a name="pidtagpriority-canonical-property"></a>PidTagPriority 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件的相对优先级。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PRIORITY  <br/> |
|标识符:  <br/> |0x0026  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>注解

不应混淆此属性和**PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md)) 属性。 重要性指示对用户的值, 而 priority 表示邮件系统软件发送邮件的顺序或速度。 较高的优先级通常表示较高的成本。 较高的重要性通常与用户界面中的不同显示相关联。
  
报告邮件的优先级应与所报告的原始邮件的优先级相同。
  
此属性可以具有下列值之一:
  
PRIO_NONURGENT 
  
> 邮件不是紧急邮件。
    
PRIO_NORMAL 
  
> 邮件具有普通优先级。
    
PRIO_URGENT 
  
> 邮件为紧急邮件。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 指定在电子邮件对象上允许的属性和操作。
    
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

