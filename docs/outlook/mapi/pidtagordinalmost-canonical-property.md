---
title: PidTagOrdinalMost 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOrdinalMost
api_type:
- COM
ms.assetid: c18de08b-8c28-4cdf-bd2e-b9c650cd6da6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 31f39cfbd0e993bfc28003fd64e8af97e7e76818
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329185"
---
# <a name="pidtagordinalmost-canonical-property"></a>PidTagOrdinalMost 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个正数, 其负值小于或等于文件夹中所有任务的**dispidTaskOrdinal** ([PidLidTaskOrdinal](pidlidtaskordinal-canonical-property.md)) 属性的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORDINAL_MOST  <br/> |
|标识符:  <br/> |0x36E2  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>注解

当文件夹中任何 task 对象的**dispidTaskOrdinal**属性更改为违反条件的方式时, 必须更新此属性以保持此条件。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 指定允许用于联系人和个人通讯组列表的属性和操作。
  
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

