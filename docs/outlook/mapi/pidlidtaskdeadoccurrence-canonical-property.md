---
title: PidLidTaskDeadOccurrence 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskDeadOccurrence
api_type:
- COM
ms.assetid: e78287ff-f8cc-45ea-8da8-e7a7359e651c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5fca47055d0c88293156483a53118667c1c72276
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574096"
---
# <a name="pidlidtaskdeadoccurrence-canonical-property"></a>PidLidTaskDeadOccurrence 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示是否必须生成新的匹配项。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskDeadOccur  <br/> |
|属性进行设置：  <br/> |PSETID_Task  <br/> |
|长 ID （盖）：  <br/> |0x00008109  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>注解

定期模式时不再有效其最后一个实例是在过去或其指定的实例数已生成。 客户端将该属性设置为 false，则新任务或为 TRUE 时，它将生成一个周期性任务的最后一个实例。 复制要生成的新实例的任务时，此属性设置为 TRUE 的副本，即已完成的实例上。
  
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

