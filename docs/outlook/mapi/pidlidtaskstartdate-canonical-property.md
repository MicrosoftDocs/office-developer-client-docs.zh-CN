---
title: PidLidTaskStartDate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskStartDate
api_type:
- COM
ms.assetid: fe87eb3d-21d1-45bb-b848-e141ce1be6a0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3bc475292e47a9ad8dd9565e17640ef95e7b3c76
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316679"
---
# <a name="pidlidtaskstartdate-canonical-property"></a>PidLidTaskStartDate 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
用户期望开始任务的日期。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskStartDate  <br/> |
|属性集：  <br/> |PSETID_Task  <br/> |
|LONG ID (的一) ：  <br/> |0x00008104  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>备注

如果此属性值未设置，则任务没有开始日期。 值"0x5AE980E0" (1，525，252，320) 还意味着任务没有开始日期。 如果任务具有开始日期，则值必须具有午夜的时间部分，并且还必须设置 **dispidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)) 和 **dispidCommonStart** ([PidLidCommonStart](pidlidcommonstart-canonical-property.md)) 属性。
  
此属性由信息标记协议规范以及位于 [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)Task-Related对象协议规范共享。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 指定对联系人和个人通讯组列表允许的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[PidLidTaskDueDate 规范属性](pidlidtaskduedate-canonical-property.md)
  
[PidLidCommonStart 规范属性](pidlidcommonstart-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

