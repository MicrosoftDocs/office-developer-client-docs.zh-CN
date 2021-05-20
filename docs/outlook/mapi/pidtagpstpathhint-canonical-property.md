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
ms.openlocfilehash: 6415ddcec2823192967b8869b46b22b58b08ba5f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437306"
---
# <a name="pidtagpstpathhint-canonical-property"></a>PidTagPstPathHint 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为配置对话框 (.pst) 个人存储表，用户可以编辑该名称。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PST_PATH_HINT、PR_PST_PATH_HINT_A、PR_PST_PATH_HINT_W  <br/> |
|标识符:  <br/> |0x6771  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |内部存储表 (.pst) 存储表  <br/> |
   
## <a name="remarks"></a>备注

如果 **PR_PST_PATH (** [PidTagPstPath](pidtagpstpath-canonical-property.md)) 属性，则配置对话框将打开，但不允许用户编辑路径和许多其他属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]] 
  
> 提供对相关协议Exchange Server的引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

