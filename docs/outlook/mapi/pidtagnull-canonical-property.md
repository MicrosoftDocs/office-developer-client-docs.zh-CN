---
title: PidTagNull 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNull
api_type:
- HeaderDef
ms.assetid: 192cdab8-c615-47b9-9f04-a1414eaf0c77
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7e9c3340dfad47a811b56c86e8e6104fb6aac7c2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329265"
---
# <a name="pidtagnull-canonical-property"></a>PidTagNull 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表示属性的 null 值或设置或保留数组空间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_NULL  <br/> |
|标识符:  <br/> |0x0000  <br/> |
|数据类型：  <br/> |PT_NULL  <br/> |
|区域：  <br/> |常见  <br/> |
   
## <a name="remarks"></a>注解

此属性用于在[SPropValue](spropvalue.md)结构的数组中保留空间。 它在[SPropTagArray](sproptagarray.md)结构的数组中使用, 以通知方法在返回的**SPropValue**结构数组中保留空间。 这允许以廉价方式填充计算属性。 
  
有关详细信息, 请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定在 "联系人" 和 "个人通讯组" 列表中允许的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

