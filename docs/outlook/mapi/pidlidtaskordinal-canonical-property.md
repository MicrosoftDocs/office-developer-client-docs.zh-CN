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
ms.openlocfilehash: 033bc038988373b11f3eac863a256717624999f9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777094"
---
# <a name="pidlidtaskordinal-canonical-property"></a>PidLidTaskOrdinal 规范属性

  
  
**适用于**： Outlook 
  
提供的辅助手段自定义排序的任务。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskOrdinal  <br/> |
|属性进行设置：  <br/> |PSETID_Task  <br/> |
|长 ID （盖）：  <br/> |0x00008123  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>说明

此属性可能仍未设置。 如果设置，其值必须大于"0x800186A0"(-2,147,383,648) 和少于"0x7FFE7960"(2,147,383,648)，并且必须唯一同一文件夹中的任务。
  
只要客户端将该属性设置为数小于负**PR_ORDINAL_MOST** ([PidTagOrdinalMost](pidtagordinalmost-canonical-property.md)) 的文件夹的属性的当前值，客户端还必须更新**PR_ORDINAL_MOST**的文件夹。 
  
文件夹的**PR_ORDINAL_MOST**属性提供高效的方法来确定在同一文件夹中的任务之间的唯一值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义模型的任务、 任务分配和任务更新电子等效项的多个对象。 
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

