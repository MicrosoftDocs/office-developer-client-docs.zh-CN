---
title: MAPI 规范属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 29151beb-7436-401a-8072-58d4facd8458
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 82c44f2292400c449ee0f82600c5b596728af7c0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590433"
---
# <a name="mapi-canonical-properties"></a>MAPI 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
规范属性是一个虚拟属性表示的 MAPI 属性或定义具有相同属性标识符的多个 MAPI 属性。 规范属性仅用于加快一致的 MAPI 属性讨论或代码之外的文档中的标识。 与 MAPI 定义已标记的属性名称不同规范属性名称不被指 MAPI 头文件中的全局常量。
  
## <a name="naming-conventions"></a>命名约定

属性规范名称开头前缀，"Pid"，表示"属性标识符"。 根据属性是否已标记的属性、 的数字标识符的命名的属性或与字符串名称的命名的属性，前缀进一步限定"PidTag，"作为"PidLid，"和"PidName"分别。 例如， [PidTagAccount](pidtagaccount-canonical-property.md)表示标记的属性，指定收件人的**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md))、 **PR_ACCOUNT_A** ([PidTagAccount](pidtagaccount-canonical-property.md)) 和**PR_ACCOUNT_W** ([PidTagAccount](pidtagaccount-canonical-property.md))帐户名;[PidLidContacts](pidlidcontacts-canonical-property.md)代表**dispidContacts**属性，具有的数字标识符，并指定一条消息; 相关联的联系人的名称的命名属性[PidNamePhishingStamp](pidnamephishingstamp-canonical-property.md)表示"http://schemas.microsoft.com/outlook/phishingstamp，"了字符串的名称，并将会出现网络钓鱼邮件标记的字符串指定的命名的属性。 
  
## <a name="representing-similar-properties-using-one-canonical-property"></a>表示使用一个规范属性类似属性

### <a name="identifying-properties-in-mapi"></a>MAPI 中的标识属性

由标识符，它是无符号的 16 位值标识 MAPI 中的所有属性。 属性标识符和属性类型 （另一个无符号 16 位值） 组成的属性的属性标记。 
  
MAPI 使用属性标记来唯一定义属性。 具有相同的属性标记，如**PR_BUSINESS2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) 和**PR_OFFICE2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) 的属性被视为相同MAPI 中的属性。 自己属性定义了 MAPI 的属性标记的列表，请参阅 Mapitags.h 的 MAPI 头文件。
  
请注意，MAPI 将分为范围的属性标识符。 标识符属于范围中的其中指示其使用情况和所有权。 0x0001 到 0x7FFF 范围中属于标记属性的属性的标识符。 在此范围内是 MAPI 定义的属性，其 0x0001 到 0x3FFF 的范围的属性的标识符。 命名的属性某范围中从 0x8000 到 0x8FFF 属性标识符。 
  
命名的属性此外特性的属性集，以及长 ID （盖），这是一个无符号的 32 位值或字符串。 属性集是一组命名属性标识与用途相似的 GUID。 属性集和盖或字符串的名称用于获取或设置的命名的属性。
  
### <a name="property-type"></a>属性类型

除了标识符，通过指定允许该属性的值的类型的数据类型归功属性。
  
属性的 string 类型，具体取决于 Unicode 基础平台中, 支持的属性可以是类型 PT_STRING8 （null 结尾的 8 位字符的字符串） 或 PT_UNICODE （null 结尾的 Unicode 字符串）。 可以使用 PT_TSTRING 类型、 定义的属性，并且根据编译设置 PT_TSTRING 默认为支持 Unicode，平台的 Unicode 字符串或 ANSI 或 DBCS 支持的平台 PT_STRING8 字符串。 很常见，字符串类型的属性是由三个类似的名称，例如**PR_ACCOUNT**、 **PR_ACCOUNT_A**和**PR_ACCOUNT_W**，这些类型的选项均进行 PT_TSTRING、 PT_STRING8 和 PT_UNICODE 分别。
  
属性类型和宏与类型相关的详细信息，请参阅 Mapidefs.h 的 MAPI 头文件。
  
### <a name="identifying-similar-properties"></a>标识类似属性

在当前的 MAPI 属性横向，不中查找已在不同的属性名称，所有这些都具有相同属性标识符已定义下公开这些属性。 例如，已标记的属性， **PR_BUSINESS2_TELEPHONE_NUMBER**和**PR_OFFICE2_TELEPHONE_NUMBER**，Mapitags.h 具有的相同属性标识符和类型中定义。 紧密相关这两个属性：
  
- **PR_BUSINESS2_TELEPHONE_NUMBER_A**
    
- **PR_BUSINESS2_TELEPHONE_NUMBER_W**
    
- **PR_OFFICE2_TELEPHONE_NUMBER_A**
    
- **PR_OFFICE2_TELEPHONE_NUMBER_W**
    
与"_A"后缀的属性的类型为 PT_STRING8，并具有"_W"后缀的类型为 PT_UNICODE。
  
规范属性，在此示例中， **PidTagBusiness2TelephoneNumber**的目的是为了方便引用使用一个标识符，此类紧密附属的 MAPI 属性和中跨所有 MAPI 以一致方式 （使用"Pid"前缀）属性。 若要查找的实际规范属性表示的 MAPI 属性，请参阅[到 MAPI 名称映射规范属性名称](mapping-canonical-property-names-to-mapi-names.md)。 若要查找与 MAPI 属性关联的规范属性，请参阅[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)。
  
## <a name="mapi-support-of-canonical-property-names"></a>MAPI 的属性规范名称的支持

因为规范属性不是真实属性，并且未定义 MAPI 头文件中，不应在代码中; 使用规范属性名称相反，您应继续在代码中使用的确切的 MAPI 属性名。 例如，可以为**PidTagBusiness2TelephoneNumber**，代码之外，请参阅**PR_BUSINESS2_TELEPHONE_NUMBER**和**PR_OFFICE2_TELEPHONE_NUMBER**并使用**PR_BUSINESS2_TELEPHONE_NUMBER**或**PR_OFFICE2_TELEPHONE_NUMBER**在代码中。 
  
如果您必须在代码中使用规范属性名称，因此您必须首先在您自己的头文件中定义它们。
  
## <a name="canonical-property-names-and-exchange-protocol-specifications"></a>规范属性名称和 Exchange 协议规范

规范名称中使用 Exchange Server 与其他 Microsoft 产品进行通信的 Microsoft Exchange Server 协议规范引用。 有关 Exchange 协议规范所引用的消息对象属性的详细信息，请参阅[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)。
  
## <a name="see-also"></a>另请参阅



[MAPI 属性标记](mapi-property-tags.md)
  
[MAPI 属性标识符概述](mapi-property-identifier-overview.md)
  
[MAPI 属性类型概述](mapi-property-type-overview.md)

