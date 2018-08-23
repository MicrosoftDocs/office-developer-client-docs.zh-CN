---
title: PidLidTaskFFixOffline 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskFFixOffline
api_type:
- COM
ms.assetid: bbaf7df4-2de0-4da3-9125-eb24dfa94cd8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 716d8b5b09ee0e29d1946042cae2631561d74df5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584651"
---
# <a name="pidlidtaskffixoffline-canonical-property"></a>PidLidTaskFFixOffline 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示**dispidTaskOwner** ([PidLidTaskOwner](pidlidtaskowner-canonical-property.md)) 属性的准确性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskFFixOffline  <br/> |
|属性进行设置：  <br/> |PSETID_Task  <br/> |
|长 ID （盖）：  <br/> |0x0000812C  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>注解

如果**dispidTaskFFixOffline**属性设置为 FALSE，或者是未设置，则**dispidTaskOwner**属性的值正确。 如果**dispidTaskFFixOffline**设置为 TRUE，客户端无法确定**dispidTaskOwner**准确值。 在这种情况下，客户端可以将**dispidTaskOwner**设置为一个通用的所有者名称，例如"Unknown"。 但是，如果客户端遇到**dispidTaskFFixOffline**值为 TRUE，并且可以确定正确的所有者名称，客户端应更新**dispidTaskOwner**并**dispidTaskFFixOffline**设置为 FALSE。 
  
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

