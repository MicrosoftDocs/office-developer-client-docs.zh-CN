---
title: MAPI 命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 464b1297-9d90-47bd-afc4-3dc63b106cb7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d83b98b4f06c648676852673a694a63b78f568b0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345862"
---
# <a name="mapi-named-properties"></a>MAPI 命名属性
 
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供了用于为属性分配名称、将这些名称映射为唯一标识符以及使此映射持久的功能。 标识符映射的永久名称可确保属性名称在会话中保持有效。
  
若要定义命名属性, 客户端或服务提供程序构成了一个名称, 并将其存储在[MAPINAMEID](mapinameid.md)结构中。 由于名称由32位全局唯一标识符 (即 GUID) 和 Unicode 字符字符串或数值组成, 因此命名属性的创建者可以创建有意义的名称, 而不会担心重复。 名称是唯一的, 可以使用它们, 而无需考虑其标识符的值。 
  
若要支持命名属性, 服务提供程序可实现两个方法 ( [IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md) ), 以便在名称和标识符之间进行转换, 并允许其[IMAPIProp:: GetProps](imapiprop-getprops.md) [IMAPIProp:: SetProps](imapiprop-setprops.md)用于检索和修改命名属性范围中的标识符的属性的方法。 命名属性标识符的范围介于0x8000 和0xFFFE 之间。 
  
任何实现**IMAPIProp**接口的对象都可以支持命名属性。 需要将来自其他提供商的条目复制到其容器中的通讯簿提供程序和可用于创建任意邮件类型的邮件存储提供程序, 以提供此支持。 对于所有其他服务提供程序, 都是一个选项。 不支持命名属性的提供程序从**GetIDsFromNames**和**GetNamesFromIDs**方法返回 MAPI_E_NO_SUPPORT, 并拒绝设置具有0x8000 或更高标识符的任何属性, 并返回 MAPI_E_UNEXPECTED 在**SPropProblemarray**。
  
为属性创建名称是客户端为现有或自定义邮件类别定义新属性的一种方法。 服务提供程序可以使用命名属性来公开其邮件系统的独特功能。 另一种用于命名属性的方法是提供另一种方法, 用于引用小于0x8000 的标识符的属性。 
  
例如, 客户端可以使用与以下代码类似的代码检索对象的所有命名属性的名称:
  
```cpp
LPSPropTagArray FAR *    lppPropTags = NULL;
LPGUID                   lpPropSetGuid = NULL;
ULONG FAR *              lpcPropNames;
LPMAPINAMEID FAR * FAR * lpppPropNames;
lpMAPIProp->GetNamesFromIDs (lppPropTags,
                             lpPropSetGuid,
                             0,
                             lpcPropNames,
                             lpppPropNames);
 
```

若要请求 PS_PUBLIC_STRINGS 属性集中的所有名称, 客户端会将属性集参数中的 NULL 替换为 PS_PUBLIC_STRINGS, 如下所示: 
  
```cpp
LPSPropTagArray FAR *    lppPropTags = NULL;
LPGUID                   lpPropSetGuid = &PS_PUBLIC_STRINGS;
ULONG FAR *              lpcPropNames;
LPMAPINAMEID FAR * FAR * lpppPropNames;
lpMAPIProp->GetNamesFromIDs (lppPropTags,
                             lpPropSetGuid,
                             0,
                             lpcPropNames,
                             lpppPropNames);
 
```

## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)

