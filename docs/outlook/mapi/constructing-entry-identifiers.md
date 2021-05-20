---
title: 构造条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bc2a9116-948e-4da3-96b8-26d73bcd63c4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8d48c2584fa5b7e862102e401ea8165821607f77
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427946"
---
# <a name="constructing-entry-identifiers"></a>构造条目标识符

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
条目标识符使用 [ENTRYID](entryid.md) 结构构造。 **ENTRYID** 结构由描述条目标识符和实际条目标识符的属性的标志组成。 
  
## <a name="entryid-structure"></a>ENTRYID 结构

**ENTRYID** 结构的定义如下： 
  
```cpp
typedef struct
{
    BYTE        abFlags[4];
    BYTE        ab[MAPI_DIM];
}  ENTRYID, FAR *LPENTRYID;
 
```

MAPI_DIM是 MapiDefs.h 头文件中定义的常量。 
  
4 字节 **abFlags** 成员的第一个字节描述条目标识符的类型和使用，并且可以具有以下值： 
  
- MAPI_NOTRECI - 指示条目标识符不能用作邮件上的收件人。
    
- MAPI_NOTRESERVED — 指示其他用户无法访问条目标识符。
    
- MAPI_NOW - 指示不能在其他时间使用条目标识符。
    
- MAPI_SHORTTERM - 指示条目标识符是短期标识符。 除非允许其他使用条目标识符，否则必须设置此字节中的所有其他值。
    
- MAPI_THISSESSION — 指示条目标识符不能用于其他会话。
    
- MAPI_NOTRESERVED — 指示条目标识符可用于其他对象的其他服务提供程序。
    
通讯簿和邮件存储提供程序创建的条目标识符的 **ab** 成员由两部分组成：一个标识服务提供商的 16 字节 [MAPIUID](mapiuid.md) 结构，一部分用于标识对象。 **MAPIUID** 是一个包含全局唯一标识符或 GUID 的结构。 GUID 是独立于字节顺序的标识符，可以使用创建 *GUID** Microsoft Visual Studio创建。 
  
在登录过程中，服务提供商在调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md)方法的过程中使用 MAPI 注册其 **MAPIUID** 结构。 当客户端调用 **OpenEntry** 方法来访问对象时，MAPI 使用 **MAPIUID** 结构来确定哪个服务提供商可以提供该访问权限。 服务提供商应针对其 DLL 的所有版本使用相同的 **MAPIUID** 结构。 这使具有较新版本的客户端能够响应使用较旧版本发送和保存的邮件。 
  
16 字节 **MAPIUID** 后的 **ab** 成员的其余部分包含特定于服务提供程序的二进制数据，用于标识特定对象。 条目标识符的此部分没有固定大小。 它可以是任何大小，在原因范围内。 服务提供商通常在其条目标识符的这一部分包含以下信息： 
  
- 版本信息 — 由于服务提供商通常将其条目标识符的格式从版本更改为版本，因此存储版本信息使快速确定如何解密任何条目标识符成为可能。
    
- 位置信息 — 位置信息是向服务提供商提供如何查找条目标识符所代表的对象的指示器的数据。 例如，服务提供商可以将最后一个位置的磁盘偏移量存储在存储该对象的数据文件中。 由于此类信息可能会随着时间的推移而更改，因此服务提供商应提供多种方式来定位其条目标识符中的对象。
    
虽然服务提供商可以回收其条目标识符，但他们应避免此做法。 如果需要重用条目标识符，服务提供商应尽可能延长在初始使用和重用之间经过的时间段。 此外，应该将条目标识符重新分配给同一类型的另一个对象。 也就是说，不应先将特定条目标识符与邮件关联，然后再与文件夹关联。
  
## <a name="see-also"></a>另请参阅



[MAPI 条目标识符](mapi-entry-identifiers.md)

