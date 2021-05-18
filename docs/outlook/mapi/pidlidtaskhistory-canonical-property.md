---
title: PidLidTaskHistory 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskHistory
api_type:
- COM
ms.assetid: 104ef21c-b607-48b7-9b06-bc53b7d9b68a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 39f2e6aeb4026f0b33be08b3bd8123283e5df3e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303008"
---
# <a name="pidlidtaskhistory-canonical-property"></a>PidLidTaskHistory 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示上次对任务进行更改的类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskHistory  <br/> |
|属性集：  <br/> |PSETID_Task  <br/> |
|LONG ID (的一) ：  <br/> |0x0000811A  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>备注

设置此属性的值时，还必须将 **dispidTaskLastUpdate** ([PidLidTaskLastUpdate](pidlidtasklastupdate-canonical-property.md)) 属性设置为当前时间。 下表显示了 **dispidTaskHistory** 属性值，按优先级递减顺序列出。 
  
|**值**|**说明**|
|:-----|:-----|
|0x00000004  <br/> |**PidLidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)) 已更改。  <br/> |
|0x00000003  <br/> |已更改另一个属性。  <br/> |
|0x00000001  <br/> |任务受理人接受此任务。  <br/> |
|0x00000002  <br/> |任务接受者拒绝了此任务。  <br/> |
|0x00000005  <br/> |任务已分配给任务分配者。  <br/> |
|0x00000000  <br/> |未做任何更改。  <br/> |
   
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

