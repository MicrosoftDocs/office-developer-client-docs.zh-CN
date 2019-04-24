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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356229"
---
# <a name="pidtagminiicon-canonical-property"></a>PidTagMiniIcon 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含窗体的半尺寸图标的位图。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MINI_ICON  <br/> |
|标识符:  <br/> |0x0FFC  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>注解

此属性包含一个图标的32×32像素的图像, 其内容与 a 的内容相同。.ico 文件, 但只有左上的16×16像素被视为有效。 此属性通常是从复制的。在表单配置文件的相应 [Description] 部分的 SmallIcon 行中指定的 .ico 文件。
  
 **注释**有些平台不支持16×16像素图标。 此属性的32×32格式在这种情况下可用, 但客户端应用程序应了解显示不一致。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagIcon 规范属性](pidtagicon-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

