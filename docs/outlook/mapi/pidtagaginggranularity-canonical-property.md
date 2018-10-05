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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390434"
---
# <a name="pidtagaginggranularity-canonical-property"></a>PidTagAgingGranularity 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
代表用于决定的项目之前的项目存档文件夹中保留的时间长度的时间单位。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_AGING_GRANULARITY  <br/> |
|标识符：  <br/> |0x36EE  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>说明

**PR_AGING_GRANULARITY**的可能值可以是下列选项之一。 
  
|**名称**|**值**|**说明**|
|:-----|:-----|:-----|
|**AG_MONTHS** <br/> |0  <br/> |**PR_AGING_PERIOD**定义中的月数。  <br/> |
|**AG_WEEKS** <br/> |1  <br/> |**PR_AGING_PERIOD**定义中的周数。  <br/> |
|**AG_DAYS** <br/> |2  <br/> |**PR_AGING_PERIOD**定义中的天数。  <br/> |
   
由两个属性， [PR_AGING_PERIOD](pidtagagingperiod-canonical-property.md)和**PR_AGING_GRANULARITY**确定的项目之前的项目存档文件夹中保留的时间长度。 **PR_AGING_PERIOD**表示项目之前对其进行存档的文件夹中保留的时间单位数。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义所使用的基本的数据结构中远程操作。
    
[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
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

