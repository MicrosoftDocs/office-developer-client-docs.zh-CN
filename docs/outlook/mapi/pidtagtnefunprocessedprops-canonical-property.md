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
ms.openlocfilehash: c25888353857f9233ba487661f5f27d64cd678cb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577427"
---
# <a name="pidtagtnefunprocessedprops-canonical-property"></a>PidTagTnefUnprocessedProps 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
筛选传输中性封装格式 (TNEF) 时，序列化属性。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TNEF_UNPROCESSED_PROPS  <br/> |
|标识符：  <br/> |0x0E9C  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 非可传送  <br/> |
   
## <a name="remarks"></a>注解

使用的 Microsoft Outlook 和 Outlook Web Access (OWA) 中的 TNEF 包含无法存储中创建的命名的属性的情况下保存原始 TNEF。
  
## <a name="related-resources"></a>相关资源

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

