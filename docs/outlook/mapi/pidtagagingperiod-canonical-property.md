---
title: PidTagAgingPeriod 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAgingPeriod
api_type:
- HeaderDef
ms.assetid: 762020d1-4bc8-d60d-0f66-3929aae24bfb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: caaa01982ff9e66fe7e17df4eaf37dcd25281d4e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569552"
---
# <a name="pidtagagingperiod-canonical-property"></a>PidTagAgingPeriod 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
代表用于确定的项目之前的项目存档文件夹中保留的时间长度的时间单位数。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_AGING_PERIOD  <br/> |
|标识符：  <br/> |0x36EC  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>注解

由两个属性， **PR_AGING_PERIOD**和**[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)** 确定的项目之前的项目存档文件夹中保留的时间长度。 **PR_AGING_GRANULARITY**表示用于**PR_AGING_PERIOD**表示，确定此时间长度时的时间单位。 
  
**PR_AGING_GRANULARITY**的可能值可以是下列选项之一。 
  
****

|**名称**|**说明**|
|:-----|:-----|
|**AG_MONTHS** <br/> |**PR_AGING_PERIOD**定义中的月数。  <br/> |
|**AG_WEEKS** <br/> |**PR_AGING_PERIOD**定义中的周数。  <br/> |
|**AG_DAYS** <br/> |**PR_AGING_PERIOD**定义中的天数。  <br/> |
   
例如，如果项目仅后已项目的文件夹中的两周，然后**PR_AGING_GRANULARITY**文件夹存档**AG_WEEKS**和**PR_AGING_PERIOD**为 2。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义所使用的基本的数据结构中远程操作。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件消息对象允许的操作。
    
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

