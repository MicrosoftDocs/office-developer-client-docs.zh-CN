---
title: PidTagRulesTable 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: fc520720-8190-4dff-8f6c-1bebf7080b57
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 945dabec4ee34d38d2474c918e779d894f4a917c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778296"
---
# <a name="pidtagrulestable-canonical-property"></a>PidTagRulesTable 规范属性

  
  
**适用于**： Outlook 
  
与所有规则应用于文件夹中包含的表。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_RULES_TABLE  <br/> |
|标识符:  <br/> |0x3FE1  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>备注

此属性是位于 Exchange 服务器上具有规则的所有 folder 对象。 包含此属性的值用于读取和修改的规则。 您可以使用具有**IID_IExchangeModifyTable**接口标识符[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法获取[IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)接口到的文件夹的规则表。 您可以使用此接口读取和修改这些规则。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。 
    
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable: IUnknown](iexchangemodifytableiunknown.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

