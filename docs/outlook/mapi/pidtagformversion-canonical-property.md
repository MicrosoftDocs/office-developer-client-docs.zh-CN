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
ms.openlocfilehash: ec806ed3ab871d6a36778b0898b2977628ccdcec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409865"
---
# <a name="pidtagformversion-canonical-property"></a>PidTagFormVersion 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含表单的版本。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_FORM_VERSION、PR_FORM_VERSION_A、PR_FORM_VERSION_W  <br/> |
|标识符:  <br/> |0x3301  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 通用  <br/> |
   
## <a name="remarks"></a>说明

这些属性指示当前对窗体有效的设计版本。 版本由窗体的设计器定义和维护, 并不一定与任何 MAPI 组件版本相关。 
  
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

