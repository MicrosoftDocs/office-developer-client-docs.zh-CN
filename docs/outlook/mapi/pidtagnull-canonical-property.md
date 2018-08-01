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
ms.openlocfilehash: 55db507055692c9e929b0125abf719d8c03ac967
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777908"
---
# <a name="pidtagnull-canonical-property"></a>PidTagNull 规范属性

  
  
**适用于**： Outlook 
  
代表一个 null 值或属性的设置，或保留数组空间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_NULL  <br/> |
|标识符：  <br/> |0x0000  <br/> |
|数据类型：  <br/> |PT_NULL  <br/> |
|区域：  <br/> |Common  <br/> |
   
## <a name="remarks"></a>说明

此属性用于保留空间数组中的[SPropValue](spropvalue.md)结构。 使用数组中的[SPropTagArray](sproptagarray.md)结构以告知保留空间返回的数组中的**SPropValue**结构的方法。 这样，计算属性便宜方式填充。 
  
有关详细信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
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

