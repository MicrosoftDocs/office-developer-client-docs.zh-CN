---
title: MAPI 规范属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 29151beb-7436-401a-8072-58d4facd8458
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4b017089a675727703de9e2ed4d584e7f77a778a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319052"
---
# <a name="mapi-canonical-properties"></a>MAPI 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
规范属性是一个虚拟属性, 表示 mapi 属性, 或使用同一属性标识符定义的多个 mapi 属性。 规范属性仅用于促进在讨论或代码外部的文档中一致标识 MAPI 属性。 与 mapi 定义的标记属性名称不同, 规范属性名称不在 MAPI 头文件中定义为全局常量。
  
## <a name="naming-conventions"></a>命名约定

规范属性名称以前缀 "Pid" 开头, 后者表示 "属性标识符"。 根据属性是否为标记属性、带有数值标识符的命名属性或具有字符串名称的命名属性, 前缀将分别被限定为 "PidTag"、"PidLid" 和 "PidName"。 例如, [PidTagAccount](pidtagaccount-canonical-property.md)表示标记属性、 **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md))、 **PR_ACCOUNT_A** ([PidTagAccount](pidtagaccount-canonical-property.md)) 和**PR_ACCOUNT_W** ([PidTagAccount](pidtagaccount-canonical-property.md)), 后者指定收件人的帐户名称;[PidLidContacts](pidlidcontacts-canonical-property.md)表示**dispidContacts**属性, 该属性具有一个数值标识符, 用于指定与邮件关联的联系人的名称;和[PidNamePhishingStamp](pidnamephishingstamp-canonical-property.md)表示 "https://schemas.microsoft.com/outlook/phishingstamp," 具有字符串名称的命名属性, 并指定标记可能是网络钓鱼的邮件的字符串。 
  
## <a name="representing-similar-properties-using-one-canonical-property"></a>使用一个规范属性表示类似的属性

### <a name="identifying-properties-in-mapi"></a>标识 MAPI 中的属性

MAPI 中的所有属性均由一个不带符号的16位值的属性标识符标识。 属性标识符和属性类型 (另一个无符号的16位值) 构成属性的属性标记。 
  
MAPI 使用属性标记来唯一定义属性。 具有相同属性标记的属性 (如**PR_BUSINESS2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) 和**PR_OFFICE2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md))) 被视为相同MAPI 中的属性。 有关 MAPI 为自己的属性定义的属性标记的列表, 请参阅 mapi 头文件 Mapitags。
  
请注意, MAPI 将属性标识符分成区域。 其中, 标识符位于范围内表示其使用和所有权。 标记属性的属性标识符位于0x0001 到0x7FFF 的范围内。 在此范围内是 MAPI 定义的属性的属性标识符, 这些属性位于0x0001 到0x3FFF 的范围中。 命名属性的属性标识符介于0x8000 和0x8FFF 之间。 
  
命名属性由属性集另外设置, 或者是 long ID (盖子), 它是一个无符号的32位值或一个字符串。 属性集是一个 GUID, 用于标识一组具有类似用途的命名属性。 属性集和盖子或字符串名称用于获取或设置命名属性。
  
### <a name="property-type"></a>属性类型

除了标识符之外, 属性的特性按指定该属性所允许的值类型的数据类型。
  
对于字符串类型的属性, 取决于对基础平台中的 Unicode 的支持, 该属性可以是类型 PT_STRING8 (以 null 结尾的8位字符串) 或 PT_UNICODE (以 null 结尾的 Unicode 字符串)。 可以使用 PT_TSTRING 类型定义属性, 并根据编译设置, PT_TSTRING 默认为支持 unicode 的平台的 Unicode 字符串, 或者是支持 ANSI 或 DBCS 的平台的 PT_STRING8 字符串。 通常情况下, 字符串类型的属性由三个相似的名称 (例如**PR_ACCOUNT**、 **PR_ACCOUNT_A**和**PR_ACCOUNT_W**) 标识, 分别为 PT_TSTRING、PT_STRING8 和 PT_UNICODE 类型。
  
有关与类型相关的属性类型和宏的详细信息, 请参阅 MAPI 头文件 mapidefs.h。
  
### <a name="identifying-similar-properties"></a>标识相似的属性

在当前 MAPI 属性的 "横向" 中, 发现某个属性在不同的属性名称下公开, 这并不常见, 它们都是用相同的属性标识符定义的。 例如, 标记属性**PR_BUSINESS2_TELEPHONE_NUMBER**和**PR_OFFICE2_TELEPHONE_NUMBER**在 Mapitags 中定义为具有相同的属性标识符和类型。 与以下两个属性密切相关:
  
- **PR_BUSINESS2_TELEPHONE_NUMBER_A**
    
- **PR_BUSINESS2_TELEPHONE_NUMBER_W**
    
- **PR_OFFICE2_TELEPHONE_NUMBER_A**
    
- **PR_OFFICE2_TELEPHONE_NUMBER_W**
    
将 "_A" 后缀的属性键入为 PT_STRING8, 并将那些具有 "_W" 后缀的属性键入为 PT_UNICODE。
  
在此示例中, 规范属性 ( **PidTagBusiness2TelephoneNumber** ) 的目的是, 使用一个标识符, 并以一致的方式 (使用 "Pid" 前缀) 在所有 MAPI 中实现更紧密关联的 mapi 属性。属性. 若要查找规范属性表示的真实 MAPI 属性, 请参阅[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)。 若要查找与 mapi 属性相关联的规范属性, 请参阅[将 mapi 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)。
  
## <a name="mapi-support-of-canonical-property-names"></a>规范属性名称的 MAPI 支持

由于规范属性不是真正的属性, 并且不是在 MAPI 头文件中定义的, 因此不应在代码中使用规范属性名称;相反, 应继续在代码中使用确切的 MAPI 属性名称。 例如, 可以将**PR_BUSINESS2_TELEPHONE_NUMBER**和**PR_OFFICE2_TELEPHONE_NUMBER**引用为**PidTagBusiness2TelephoneNumber**, 并使用**PR_BUSINESS2_TELEPHONE_NUMBER**或 PR_OFFICE2_ 的代码之外的代码。 **** 代码中的 TELEPHONE_NUMBER。 
  
如果您必须在代码中使用规范属性名称, 则必须先在您自己的头文件中定义它们。
  
## <a name="canonical-property-names-and-exchange-protocol-specifications"></a>规范属性名称和 Exchange 协议规范

规范名称在 exchange server 用于与其他 Microsoft 产品通信的 microsoft Exchange server 协议规范中引用。 有关 Exchange 协议规范所引用的邮件对象属性的详细信息, 请参阅[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)。
  
## <a name="see-also"></a>另请参阅



[MAPI 属性标记](mapi-property-tags.md)
  
[MAPI 属性标识符概述](mapi-property-identifier-overview.md)
  
[MAPI 属性类型概述](mapi-property-type-overview.md)

