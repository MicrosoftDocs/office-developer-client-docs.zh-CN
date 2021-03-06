---
title: PidTagLongTermEntryIdFromTable 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLongTermEntryIdFromTable
api_type:
- HeaderDef
ms.assetid: d9457fea-4b1e-4cf6-9c4b-14c98fbec2a1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 574c7d305f105709aebcd41e30b034fbac1892a9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425664"
---
# <a name="pidtaglongtermentryidfromtable-canonical-property"></a>PidTagLongTermEntryIdFromTable 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
获取项目的长期条目标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_LONGTERM_ENTRYID_FROM_TABLE  <br/> |
|标识符:  <br/> |0x6670  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |表属性  <br/> |
   
## <a name="remarks"></a>备注

此属性可在内容表中使用，以作为长期条目标识符（而不是短期条目标识符）获取项的条目标识符。 有关长期和短期标识符的信息，请参阅 PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

