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
ms.openlocfilehash: d42b58bf4fd445f34064b179c873c8bc15b11b3f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360114"
---
# <a name="pidtagagingperiod-canonical-property"></a>PidTagAgingPeriod 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表示用于确定项目在存档前保留在文件夹中的时间长度的时间单位。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_AGING_PERIOD  <br/> |
|标识符:  <br/> |0x36EC  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>备注

项目在存档项目之前保留在文件夹中的时间长度由两个属性决定，即 PR_AGING_PERIOD **和****[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)**。 **PR_AGING_GRANULARITY** 表示确定此时间长度 **PR_AGING_PERIOD** 表示时间单位。 
  
此参数 **PR_AGING_GRANULARITY** 可以是下列值之一。 
  
****

|**名称**|**说明**|
|:-----|:-----|
|**AG_MONTHS** <br/> |**PR_AGING_PERIOD** 以月数定义。  <br/> |
|**AG_WEEKS** <br/> |**PR_AGING_PERIOD** 以周数定义。  <br/> |
|**AG_DAYS** <br/> |**PR_AGING_PERIOD** 天数进行定义。  <br/> |
   
例如，如果某个文件夹仅在项目在文件夹中保存了两周后存档该项目，则PR_AGING_GRANULARITY为 AG_WEEKS，PR_AGING_PERIOD为 2。  
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义远程操作中使用的基本数据结构。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许电子邮件对象使用的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

