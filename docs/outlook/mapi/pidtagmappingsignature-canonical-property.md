---
title: PidTagMappingSignature 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMappingSignature
api_type:
- HeaderDef
ms.assetid: a5e9f807-12a9-4bc9-a6a5-17579e747ffa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d12e8510686f51698981c47327f79ef40d3ec342
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396223"
---
# <a name="pidtagmappingsignature-canonical-property"></a>PidTagMappingSignature 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含特定 MAPI 对象的命名属性的映射签名。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MAPPING_SIGNATURE  <br/> |
|标识符：  <br/> |0x0FF8  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>说明

建议具有命名属性的对象公开此属性。 客户端应用程序应该检查这两个对象的**PR_MAPPING_SIGNATURE**属性时复制命名到另一个对象的属性。 使用此属性可以减少翻译之间复制的属性的名称和标识符。 
  
如果给定 MAPI 对象，该属性不存在，该对象将具有其自己的名称和标识符的唯一映射。 在这种情况下客户端必须对源对象，然后对目标对象的[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法调用[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)方法。 
  
当两个对象具有相同的**PR_MAPPING_SIGNATURE**值时，则不需要翻译名称标识符和标识符名称与客户端。 客户端可以只需调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法对源和[IMAPIProp::SetProps](imapiprop-setprops.md)方法在目标位置。 这很方便的客户端的执行的命名属性的自定义复制和提供程序实现的[IMAPIProp::CopyTo](imapiprop-copyto.md)和[IMAPIProp::CopyProps](imapiprop-copyprops.md)方法。 
  
命名的属性和映射的名称和标识符的详细信息，请参阅[MAPI 命名属性](mapi-named-properties.md)。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPINAMEID](mapinameid.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

