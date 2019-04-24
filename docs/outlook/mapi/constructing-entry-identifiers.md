---
title: 构建条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bc2a9116-948e-4da3-96b8-26d73bcd63c4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8d48c2584fa5b7e862102e401ea8165821607f77
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335089"
---
# <a name="constructing-entry-identifiers"></a>构建条目标识符

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
条目标识符是使用[ENTRYID](entryid.md)结构构造的。 **ENTRYID**结构由描述条目标识符和实际条目标识符的属性的标志组成。 
  
## <a name="entryid-structure"></a>ENTRYID 结构

**ENTRYID**结构定义如下: 
  
```cpp
typedef struct
{
    BYTE        abFlags[4];
    BYTE        ab[MAPI_DIM];
}  ENTRYID, FAR *LPENTRYID;
 
```

MAPI_DIM 是在 mapidefs.h 头文件中定义的常量。 
  
4字节**abFlags**成员的第一个字节描述了条目标识符的类型和使用, 并且可以具有以下值: 
  
- MAPI_NOTRECI —指示不能将条目标识符用作邮件的收件人。
    
- MAPI_NOTRESERVED —指示其他用户无法访问条目标识符。
    
- MAPI_NOW —指示不能在其他时间使用条目标识符。
    
- MAPI_SHORTTERM —指示条目标识符是短期的。 除非允许其他使用条目标识符, 否则必须设置此字节中的所有其他值。
    
- MAPI_THISSESSION —指示条目标识符不能用于其他会话。
    
- MAPI_NOTRESERVED —指示其他对象的其他服务提供程序可以使用条目标识符。
    
由通讯簿和邮件存储提供程序创建的条目标识符的**ab**成员由两部分组成: 一个标识服务提供程序的16字节[MAPIUID](mapiuid.md)结构, 以及一个标识该对象的部分。 **MAPIUID**是一个包含全局唯一标识符或 GUID 的结构。 GUID 是一种独立于字节顺序的标识符, 可以使用 Microsoft Visual Studio*Create GUID** 工具创建。 
  
在登录过程中, 服务提供商在调用[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)方法期间, 在登录过程中向 MAPI 注册其**MAPIUID**结构。 当客户端调用**OpenEntry**方法访问对象时, MAPI 将使用**MAPIUID**结构来确定哪些服务提供商可以提供该访问权限。 服务提供程序应对其 DLL 的所有版本使用相同的**MAPIUID**结构。 这使具有较新版本的客户端能够响应随旧版本发送和保存的邮件。 
  
16字节**MAPIUID**后面的**ab**成员的其余部分包含用于标识特定对象的特定于服务提供程序的二进制数据。 此部分条目标识符没有固定大小。 它可以是任何大小, 在某个原因内。 服务提供程序通常在此部分的条目标识符中包含以下信息: 
  
- 版本信息-由于服务提供程序会将其条目标识符的格式从版本更改为版本, 因此存储版本信息可以快速确定如何解密任何条目标识符。
    
- 位置信息—位置信息是为服务提供商提供一个指标的数据, 该指标指示如何查找条目标识符所代表的对象。 例如, 服务提供程序可以将磁盘偏移量存储在存储对象的数据文件中的最后一个位置。 由于此类信息可以随着时间的推移而发生变化, 因此服务提供商应提供多种方法来查找其条目标识符中的对象。
    
尽管服务提供商可以回收其条目标识符, 但应避免这种做法。 如果需要重用条目标识符, 则服务提供商应将初始使用和重用之间的时间间隔设置为尽可能长的时间。 此外, 还应将条目标识符重新分配给同一类型的另一个对象。 也就是说, 特定条目标识符不应首先与邮件相关联, 然后再与文件夹相关联。
  
## <a name="see-also"></a>另请参阅



[MAPI 条目标识符](mapi-entry-identifiers.md)

