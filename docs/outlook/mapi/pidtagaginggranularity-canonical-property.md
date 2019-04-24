---
title: PidTagAgingGranularity 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAgingGranularity
api_type:
- HeaderDef
ms.assetid: b79ec87d-d97c-4e6c-899b-78ebf1b485a7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b4006b62758b32598a64eaa4eb333c7ce5b12605
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325583"
---
# <a name="pidtagaginggranularity-canonical-property"></a>PidTagAgingGranularity 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表示用于确定项目在存档项目之前保留在该文件夹中的时间长度时使用的时间单位。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_AGING_GRANULARITY  <br/> |
|标识符:  <br/> |0x36EE  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>注解

**PR_AGING_GRANULARITY**的可能值可以是下列值之一。 
  
|**Name**|**Value**|**说明**|
|:-----|:-----|:-----|
|**AG_MONTHS** <br/> |0  <br/> |**PR_AGING_PERIOD**是在月数内定义的。  <br/> |
|**AG_WEEKS** <br/> |1  <br/> |**PR_AGING_PERIOD**是在周数内定义的。  <br/> |
|**AG_DAYS** <br/> |双面  <br/> |**PR_AGING_PERIOD**是在天数内定义的。  <br/> |
   
项目在存档项目之前保留在文件夹中的时间长度由两个属性[PR_AGING_PERIOD](pidtagagingperiod-canonical-property.md)和**PR_AGING_GRANULARITY**确定。 **PR_AGING_PERIOD**表示项目在存档前保留在文件夹中的时间单位的数量。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义在远程操作中使用的基本数据结构。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
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

