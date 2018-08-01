---
title: MAPI 命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 464b1297-9d90-47bd-afc4-3dc63b106cb7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e755c18ef3cc32f9a00169f19cf336eace447a32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776271"
---
# <a name="mapi-named-properties"></a>MAPI 命名属性
 
**适用于**： Outlook 
  
MAPI 提供的工具，用于为属性分配名称、 将这些名称映射到唯一标识符，以及使此映射持久。 永久名称标识符映射到可确保跨会话保持有效属性名称。
  
若要定义的命名的属性，客户端或服务提供程序构成一个名称，并将其存储在[MAPINAMEID](mapinameid.md)结构中。 由于名称组成的 32 位的全局唯一标识符，或 GUID，以及任一 Unicode 字符字符串或数字值的命名属性的创建者可以创建有意义的名称，而不必担心重复。 名称是唯一的而不考虑其标识符的值可以使用它们。 
  
若要支持命名的属性，一个服务提供程序实现两种方法 — [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) — 名称和标识符之间翻译并允许其[IMAPIProp::GetProps](imapiprop-getprops.md) [IMAPIProp::SetProps](imapiprop-setprops.md)方法来检索和修改与命名的属性区域中的标识符的属性。 命名的属性标识符的范围是 0x8000 和 0xFFFE 之间。 
  
实现**IMAPIProp**接口的任何对象才能支持命名的属性。 通讯簿提供程序使其他提供程序复制到其容器和消息中的条目存储提供程序可用于创建任意消息类型需要提供此支持。 它是所有其他服务提供程序选项。 提供程序不支持的命名属性返回 MAPI_E_NO_SUPPORT 从**GetIDsFromNames**和**GetNamesFromIDs**方法和拒绝**中设置的 0x8000 或更高版本，使其返回 MAPI_E_UNEXPECTED 标识符与任何属性SPropProblemarray**。
  
创建属性的名称是一种方法的客户端可以定义为现有或自定义邮件类的新属性。 服务提供商可以使用命名的属性公开其邮件系统的独特功能。 尚未命名属性的另一个用于旨在提供用小于 0x8000 标识符属性中引用的另一种方法。 
  
例如，客户端无法使用类似于下面的代码的代码检索所有对象的命名属性的名称：
  
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

要从 PS_PUBLIC_STRINGS 属性集申请所有名称，客户端将如下所示替换 PS_PUBLIC_STRINGS 的属性集参数中的 NULL: 
  
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

