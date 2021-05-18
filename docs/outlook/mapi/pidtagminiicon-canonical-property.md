---
title: PidTagMiniIcon 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMiniIcon
api_type:
- HeaderDef
ms.assetid: a436b590-63f3-413c-a9c2-7664567e0ff0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ea7f9e0ed57c56b48399b9ffd1ea42db28daf249
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405413"
---
# <a name="pidtagminiicon-canonical-property"></a>PidTagMiniIcon 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含窗体的半尺寸图标的位图。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MINI_ICON  <br/> |
|标识符:  <br/> |0x0FFC  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此属性包含图标的 32 × 32 像素图像，与 的内容相同。ICO 文件，但只有左上角 16 × 16 像素被视为重要文件。 此属性通常从 复制。在表单配置文件的适当 [Description] 节的 SmallIcon 行中指定的 ICO 文件。
  
 **注意** 某些平台不支持 16 × 16 像素图标。 此属性的 32 × 32 格式在这种情况下可用，但客户端应用程序应注意显示不一致。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagIcon 规范属性](pidtagicon-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

