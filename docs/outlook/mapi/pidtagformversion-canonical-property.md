---
title: PidTagFormVersion 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFormVersion
api_type:
- HeaderDef
ms.assetid: f2220060-65ea-4969-88d7-8348bd5aa242
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3790ce243890f1cce4d67352a8fb0b7191588269
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777656"
---
# <a name="pidtagformversion-canonical-property"></a>PidTagFormVersion 规范属性

  
  
**适用于**： Outlook 
  
包含为表单的版本。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FORM_VERSION，PR_FORM_VERSION_A，PR_FORM_VERSION_W  <br/> |
|标识符：  <br/> |0x3301  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常见的 MAPI  <br/> |
   
## <a name="remarks"></a>说明

这些属性指示哪些设计版本是当前在窗体的效果。 定义和维护表单版本的设计器，并不一定与任何 MAPI 组件版本。 
  
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

