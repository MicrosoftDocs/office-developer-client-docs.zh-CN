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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342537"
---
# <a name="pidtagmappingsignature-canonical-property"></a>PidTagMappingSignature 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含特定 MAPI 对象的命名属性的映射签名。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MAPPING_SIGNATURE  <br/> |
|标识符:  <br/> |0x0FF8  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>备注

建议具有命名属性的对象公开此属性。 在将命名属性 **从一个对象PR_MAPPING_SIGNATURE** 另一个对象时，客户端应用程序应检查这两个对象的 PR_MAPPING_SIGNATURE 属性。 使用此属性可以最大程度地减少复制的属性的名称和标识符之间的转换。 
  
如果给定 MAPI 对象不存在此属性，则该对象具有其自己的名称和标识符的唯一映射。 在这种情况下，客户端必须对源对象调用 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 方法，然后在目标对象上调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法。 
  
当两个对象具有相同的PR_MAPPING_SIGNATURE值时，客户端无需将名称转换为标识符，而将标识符转换为名称。 客户端只需对源调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法，然后在目标上调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法。 这便于执行命名属性的自定义复制的客户端，以及实现 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 和 [IMAPIProp：：CopyProps 方法的提供程序](imapiprop-copyprops.md) 。 
  
有关命名属性以及名称和标识符映射的信息，请参阅 [MAPI Named Properties](mapi-named-properties.md)。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPINAMEID](mapinameid.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

