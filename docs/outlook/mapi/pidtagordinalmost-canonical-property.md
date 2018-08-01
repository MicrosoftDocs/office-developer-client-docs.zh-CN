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
ms.openlocfilehash: 0c2cf784ff9a86c9e2a2ce1a25b3c4b8ff7d8b75
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777909"
---
# <a name="pidtagordinalmost-canonical-property"></a>PidTagOrdinalMost 规范属性

  
  
**适用于**： Outlook 
  
包含的正数其负小于或等于文件夹中的所有任务的**dispidTaskOrdinal** ([PidLidTaskOrdinal](pidlidtaskordinal-canonical-property.md)) 属性的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORDINAL_MOST  <br/> |
|标识符：  <br/> |0x36E2  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>说明

此属性必须更新维护这种情况，只要文件夹中的任何任务对象的**dispidTaskOrdinal**属性更改冲突条件的方式。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
  
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

