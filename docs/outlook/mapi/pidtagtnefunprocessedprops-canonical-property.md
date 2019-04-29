---
title: PidTagTnefUnprocessedProps 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTnefUnprocessedProps
api_type:
- COM
ms.assetid: df9cd614-1198-44a2-9bf5-36c57179a9a9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9ea9938ca9f8dd0b25cf2de5199178a76e17b6d0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431321"
---
# <a name="pidtagtnefunprocessedprops-canonical-property"></a>PidTagTnefUnprocessedProps 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
筛选传输中性封装格式 (TNEF) 时序列化属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TNEF_UNPROCESSED_PROPS  <br/> |
|标识符:  <br/> |0x0E9C  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 非传输  <br/> |
   
## <a name="remarks"></a>说明

Microsoft outlook 和 Outlook Web Access (OWA) 用于保存原始 tnef, 在 TNEF 中包含无法在存储中创建的命名属性的情况下。
  
## <a name="related-resources"></a>相关资源

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

