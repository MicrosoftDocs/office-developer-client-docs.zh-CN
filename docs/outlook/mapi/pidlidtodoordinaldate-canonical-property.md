---
title: PidLidToDoOrdinalDate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidToDoOrdinalDate
api_type:
- COM
ms.assetid: b6a500fc-07f4-4788-ae46-d179a96a48e2
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: d708424ccb15be15746fe8a33eea73a8e0f99323
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777122"
---
# <a name="pidlidtodoordinaldate-canonical-property"></a>PidLidToDoOrdinalDate 规范属性

  
  
**适用于**： Outlook 
  
确定合并待办事项列表中的对象的排序顺序。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |dispidToDoOrdinalDate  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x000085A0  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>备注

标记对象后，此属性应设置为当前时间以协调世界时 (UTC)。 
  
如果客户端允许用户重新排序通过拖动合并的任务列表或其他机制中的任务，这些用户可以使用任何合适的算法，以便此属性用作 sor 在正确的位置显示任务确定此属性的新值做到的一字段。
  
当此属性用于对对象和领结排序结果进行排序时， **dispidToDoSubOrdinal** ([PidLidToDoSubOrdinal](pidlidtodosubordinal-canonical-property.md)) 属性用作领结分词系统。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定的属性和与标记的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[PidLidToDoSubOrdinal 规范属性](pidlidtodosubordinal-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

