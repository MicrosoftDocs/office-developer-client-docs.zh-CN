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
ms.openlocfilehash: 2fc605c57936765f43d7a6941dcc8d40d058db2f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540474"
---
# <a name="mapi-canonical-properties"></a>MAPI 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
规范属性是一个代表 MAPI 属性的虚拟属性，或者是使用同一属性标识符定义的多个 MAPI 属性。 规范属性仅用于促进在讨论或代码中对 MAPI 属性进行一致的标识。 与 MAPI 定义的带标记的属性名称不同，规范属性名称不会在 MAPI 头文件中定义为全局常量。
  
## <a name="naming-conventions"></a>命名约定

规范属性名称以前缀"Pid"开头，它表示"属性标识符"。 根据该属性是带标记的属性、具有数字标识符的命名属性还是具有字符串名称的命名属性，前缀将被分别进一步限定为"PidTag"、"PidLid"和"PidName"。 例如 [，PidTagAccount](pidtagaccount-canonical-property.md)表示指定收件人帐户名称的带标记属性 PR_ACCOUNT **(** [PidTagAccount](pidtagaccount-canonical-property.md)) 、PR_ACCOUNT_A ([PidTagAccount](pidtagaccount-canonical-property.md)) 和 **PR_ACCOUNT_W** ([PidTagAccount](pidtagaccount-canonical-property.md)) ; [PidLidContacts](pidlidcontacts-canonical-property.md)表示 **dispidContacts** 属性，一个命名属性，具有数字标识符，并指定与邮件相关联的联系人的名称;和 [PidNamePhishingStamp](pidnamephishingstamp-canonical-property.md)表示"，"，一个命名属性，具有一个字符串名称，并指定标记可能是网络钓鱼 http://schemas.microsoft.com/outlook/phishingstamp 邮件的字符串。 
  
## <a name="representing-similar-properties-using-one-canonical-property"></a>使用一个规范属性表示类似的属性

### <a name="identifying-properties-in-mapi"></a>标识 MAPI 中的属性

MAPI 中所有属性都由无符号 16 位值的属性标识符标识。 属性标识符和属性类型 (另一个未签名的 16 位) 构成属性的属性标记。 
  
MAPI 使用属性标记唯一地定义属性。 具有相同属性标记的属性（如 **PR_BUSINESS2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) 和 **PR_OFFICE2_TELEPHONE_NUMBER** ([PidTagBusiness2TelephoneNumber](pidtagbusiness2telephonenumber-canonical-property.md)) ）在 MAPI 中被视为相同的属性。 有关 MAPI 为其自身的属性定义的属性标记的列表，请参阅 MAPI 头文件 Mapitags.h。
  
请注意，MAPI 将属性标识符划分为范围。 标识符在范围中的何处指示其使用和所有权。 标记属性的属性标识符位于0x0001 0x7FFF。 在此范围内是 MAPI 定义属性的属性标识符，这些属性属于0x0001范围0x3FFF。 命名属性的属性标识符的范围从 0x8000 到 0x8FFF。 
  
命名属性还由属性集和一个长 ID (一个（无符号的 32 位值）) 一个 LONG ID 或一个字符串。 属性集是标识一组具有相似用途的命名属性的 GUID。 属性集和一个或多个 STRING 名称用于获取或设置命名属性。
  
### <a name="property-type"></a>属性类型

除标识符外，属性由指定该属性数据类型类型的属性。
  
对于字符串类型的属性，该属性的类型可以是 PT_STRING8 (以 null 结尾的 8 位字符字符串) 或 PT_UNICODE (以 null 结尾的 Unicode 字符串) 。 可以使用 PT_TSTRING 类型定义属性，根据编译设置，PT_TSTRING 默认为支持 Unicode 的平台的 Unicode 字符串，或者支持 ANSI 或 DBCS 的平台的 PT_STRING8 字符串。 通常，字符串类型属性由三个相似的名称（如 **PR_ACCOUNT、PR_ACCOUNT_A** 和 **PR_ACCOUNT_W）** 标识，它们分别类型为 PT_TSTRING、PT_STRING8 和 PT_UNICODE。
  
有关与类型相关的属性类型和宏详细信息，请参阅 MAPI 头文件 Mapidefs.h。
  
### <a name="identifying-similar-properties"></a>标识相似属性

在当前 MAPI 属性的横向，发现一个属性已在不同的属性名称下公开，所有这些名称都使用相同的属性标识符进行定义的情况很常见。 例如，标记属性 **（PR_BUSINESS2_TELEPHONE_NUMBER** 和 **PR_OFFICE2_TELEPHONE_NUMBER**）在 Mapitags.h 中定义，以具有相同的属性标识符和类型。 与这两个属性密切相关的有：
  
- **PR_BUSINESS2_TELEPHONE_NUMBER_A**
    
- **PR_BUSINESS2_TELEPHONE_NUMBER_W**
    
- **PR_OFFICE2_TELEPHONE_NUMBER_A**
    
- **PR_OFFICE2_TELEPHONE_NUMBER_W**
    
具有"_A"后缀的属性类型为 PT_STRING8，具有"_W"后缀的属性类型为 PT_UNICODE。
  
规范属性（此示例中为 **PidTagBusiness2TelephoneNumber）** 的目的是为了便于使用一个标识符引用这种紧密关联 MAPI 属性，并便于在所有 MAPI 属性之间使用"Pid"前缀 (以一致的方式引用) 。 若要查找规范属性表示哪些真实的 MAPI 属性，请参阅将规范属性名称映射到 [MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)。 若要查找 MAPI 属性与之关联的规范属性，请参阅[MapI Names to Canonical Property Names。](mapping-mapi-names-to-canonical-property-names.md)
  
## <a name="mapi-support-of-canonical-property-names"></a>对规范属性名称的 MAPI 支持

由于规范属性不是真实属性，并且未在 MAPI 头文件中定义，因此不应在代码中使用规范属性名称;相反，你应该继续在代码中使用确切的 MAPI 属性名称。 例如，可以将代码 **PR_BUSINESS2_TELEPHONE_NUMBER** **PidTagBusiness2TelephoneNumber** PR_OFFICE2_TELEPHONE_NUMBER代码外部的 PR_BUSINESS2_TELEPHONE_NUMBER 和 PR_OFFICE2_TELEPHONE_NUMBER 代码。   
  
如果您必须在代码中使用规范属性名称，则必须先在您自己的头文件中定义它们。
  
## <a name="canonical-property-names-and-exchange-protocol-specifications"></a>规范属性名称和Exchange协议规范

规范名称在 Microsoft Exchange Server协议规范中引用，Exchange Server用于与其他 Microsoft 产品进行通信。 有关由协议规范引用的邮件对象Exchange，请参阅[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)。
  
## <a name="see-also"></a>另请参阅



[MAPI 属性标记](mapi-property-tags.md)
  
[MAPI 属性标识符概述](mapi-property-identifier-overview.md)
  
[MAPI 属性类型概述](mapi-property-type-overview.md)

