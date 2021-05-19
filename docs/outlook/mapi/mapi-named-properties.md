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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435045"
---
# <a name="mapi-named-properties"></a>MAPI 命名属性
 
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供了一个向属性分配名称、将这些名称映射到唯一标识符以及使此映射持久化功能。 永久性名称到标识符的映射可确保属性名称在会话间保持有效。
  
为了定义命名属性，客户端或服务提供商会创建一个名称，并存储到 [MAPINAMEID](mapinameid.md) 结构中。 由于名称由 32 位全局唯一标识符或 GUID 以及 Unicode 字符串或数值组成，命名属性的创建者可以创建有意义的名称，而不会担心重复。 名称是唯一的，可以在不考虑其标识符值的情况下使用。 
  
为了支持命名属性，服务提供商实现了 [两种方法（IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 和 [IMAPIProp：：GetNamesFromIDs）](imapiprop-getnamesfromids.md) 在名称和标识符之间转换，并允许 [其 IMAPIProp：：GetProps](imapiprop-getprops.md)[IMAPIProp：：SetProps](imapiprop-setprops.md) 方法检索和修改具有命名属性范围中的标识符的属性。 命名属性标识符的范围介于 0x8000 和 0xFFFE。 
  
实现 **IMAPIProp** 接口的任何对象都可以支持命名属性。 需要允许将来自其他提供程序的条目复制到其容器和可用于创建任意邮件类型的邮件存储提供程序的通讯簿提供程序才能提供此支持。 它是所有其他服务提供商的一个选项。 不支持命名属性的提供程序从 **GetIDsFromNames** 和 **GetNamesFromIDs** 方法返回 MAPI_E_NO_SUPPORT，并拒绝设置标识符为 0x8000 或更高的任何属性，在 **SPropProblemarray** 中返回 MAPI_E_UNEXPECTED。
  
为属性创建名称是客户端定义现有或自定义邮件类的新属性的一种方法。 服务提供商可以使用命名属性来公开其邮件系统的独特功能。 不过，命名属性的另一个用途是提供引用以下属性的标识符的0x8000。 
  
例如，客户端可以使用类似于以下代码的代码来检索对象的所有命名属性的名称：
  
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

若要从属性集PS_PUBLIC_STRINGS所有名称，客户端将替换属性集参数中的 NULL，PS_PUBLIC_STRINGS如下所示： 
  
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

