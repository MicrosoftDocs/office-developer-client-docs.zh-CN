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
ms.openlocfilehash: 5514e0553f719e2e875aad7001bb38a6a52e8e08
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589775"
---
# <a name="pidtagminiicon-canonical-property"></a>PidTagMiniIcon 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含半尺寸图标的窗体的位图。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MINI_ICON  <br/> |
|标识符：  <br/> |0x0FFC  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

此属性包含一个图标，相同的内容的 32 × 32 像素图像。ICO 文件，但只有左上方 16x16 像素视为重要。 此属性通常从复制。ICO SmallIcon 行的窗体配置文件的适当 [描述] 节中指定的文件。
  
 **注释**某些平台执行不支持 16x16 像素的图标。 此属性的 32 × 32 格式是这种情况下可用，但客户端应用程序应注意的显示不一致。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagIcon 规范属性](pidtagicon-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

