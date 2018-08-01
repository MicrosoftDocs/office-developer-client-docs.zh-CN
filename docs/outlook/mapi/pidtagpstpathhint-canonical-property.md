---
title: PidTagPstPathHint 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 9cb4af50-3735-4029-a608-a6e7927019dd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 295b20ebc0c41104a8b1c8e46e2064c3ef32f99e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778109"
---
# <a name="pidtagpstpathhint-canonical-property"></a>PidTagPstPathHint 规范属性

  
  
**适用于**： Outlook 
  
提供用于配置对话框的用户可以编辑的个人存储表 （.pst 文件） 名称。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PST_PATH_HINT，PR_PST_PATH_HINT_A，PR_PST_PATH_HINT_W  <br/> |
|标识符：  <br/> |0x6771  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |个人存储表 (.pst) 内部  <br/> |
   
## <a name="remarks"></a>说明

如果改为使用**PR_PST_PATH** ([PidTagPstPath](pidtagpstpath-canonical-property.md)) 属性，则配置对话框将打开，但不是将允许用户编辑的路径和多个其他属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]] 
  
> 提供了相关的 Exchange Server 协议规范参考。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

