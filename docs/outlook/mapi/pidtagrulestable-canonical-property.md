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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e1c670cd566e838104ae3d5480c2297f8632d899
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428499"
---
# <a name="pidtagrulestable-canonical-property"></a>PidTagRulesTable 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个表，该表包含应用于文件夹的所有规则。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RULES_TABLE  <br/> |
|标识符:  <br/> |0x3FE1  <br/> |
|数据类型：  <br/> |PT_OBJECT  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>备注

此属性存在于具有规则的文件夹Exchange Server上的所有文件夹对象上。 此属性中包含的值用于读取和修改规则。 可以将 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法与 **IID_IExchangeModifyTable** 接口标识符一同使用，以获取文件夹上规则表的 [IExchangeModifyTable ： IUnknown](iexchangemodifytableiunknown.md) 接口。 您可以使用此接口读取和修改这些规则。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。 
    
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

