---
title: PidLidTaskOrdinal 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskOrdinal
api_type:
- COM
ms.assetid: 1021860e-4c40-4c22-aa68-b568d046aaf7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a64008da93584529916a9303176bba0aa08d3fac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357958"
---
# <a name="pidlidtaskordinal-canonical-property"></a>PidLidTaskOrdinal 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
帮助执行自定义排序任务。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskOrdinal  <br/> |
|属性集：  <br/> |PSETID_Task  <br/> |
|LONG ID (的一) ：  <br/> |0x00008123  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>备注

此属性可能未设置。 如果设置，则其值必须大于"0x800186A0" (-2，147，383，648) 且小于"0x7FFE7960" (2，147，383，648) 并且在同一文件夹中的任务之间必须是唯一的。
  
每当客户端将此属性设置为小于文件夹的 **PR_ORDINAL_MOST** ([PidTagOrdinalMost](pidtagordinalmost-canonical-property.md)) 属性的当前值的负数时，客户端还必须更新文件夹上的 **PR_ORDINAL_MOST。** 
  
文件夹 **PR_ORDINAL_MOST** 属性提供了一种有效方法，可确定同一文件夹中的任务之间的唯一值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。 
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

