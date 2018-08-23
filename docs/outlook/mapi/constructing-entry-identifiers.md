---
title: 构建条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bc2a9116-948e-4da3-96b8-26d73bcd63c4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f15749077596bd6c89828eb730cadd5624a75fe1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564582"
---
# <a name="constructing-entry-identifiers"></a>构建条目标识符

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
使用[ENTRYID](entryid.md)结构构建条目标识符。 **ENTRYID**结构组成描述的项标识符和实际的项标识符的属性的标志。 
  
## <a name="entryid-structure"></a>ENTRYID 结构

**ENTRYID**结构定义如下： 
  
```cpp
typedef struct
{
    BYTE        abFlags[4];
    BYTE        ab[MAPI_DIM];
}  ENTRYID, FAR *LPENTRYID;
 
```

MAPI_DIM 是 MapiDefs.h 标头文件中定义的常量。 
  
4 字节**abFlags**成员的第一个字节描述的类型和使用的项标识符可以具有下列值： 
  
- MAPI_NOTRECI — 指示条目标识符不能用作邮件收件人。
    
- MAPI_NOTRESERVED — 指示其他用户无法访问的项标识符。
    
- 在其他情况下不能使用的项标识符的 MAPI_NOW — 指示。
    
- 项标识符是短期 MAPI_SHORTTERM — 指示。 必须设置此字节中的所有其他值，除非在内的项标识符的其他用途。
    
- MAPI_THISSESSION — 指示上其他会话不能使用的项标识符的。
    
- MAPI_NOTRESERVED — 指示的项标识符可用于其他服务提供程序的其他对象。
    
地址簿和消息存储提供程序创建的项标识符的**ab**成员是两个部分组成： 标识服务提供商和一段来标识对象的 16 字节[MAPIUID](mapiuid.md)结构。 **MAPIUID**是包含的全局唯一标识符或 GUID 的结构。 GUID 是一个独立于字节的顺序的标识符，可以使用 Microsoft Visual Studio*创建 GUID*创建 * 工具。 
  
服务提供商注册 MAPI 登录过程中对[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法的调用中其**MAPIUID**结构。 当客户端调用**OpenEntry**方法来访问的对象时，MAPI 使用**MAPIUID**结构确定哪项服务提供程序可以提供访问。 服务提供商应使用相同的**MAPIUID**结构的所有版本的其 DLL。 这样，客户端与新版本以响应发送和使用较旧版本保存的邮件。 
  
**Ab**成员后 16 字节**MAPIUID**包含特定对象标识服务提供程序特定二进制数据的其余部分。 没有固定的大小的项标识符的此部分。 它可以是任何大小、 内原因。 服务提供商通常包括其条目标识符本部分中的以下信息： 
  
- 版本信息 — 的情况很常见的服务提供商，若要更改其条目标识符格式版本之间的差异，因为存储版本信息使得快速确定如何解密任何条目标识符。
    
- 位置信息 — 位置信息是提供如何查找所表示的项标识符的对象的指示符的服务提供商的数据。 例如，服务提供商可以存储的数据文件已存储对象中的最后一个地方偏移的磁盘。 此类型的信息可随时间变化的因为服务提供商应为其条目 identifiers 中查找对象提供多种方式。
    
尽管服务提供商可以回收站其条目标识符，但它们应避免这种做法。 如有必要可重用的项标识符，服务提供商应进行回拨此前初始使用和重用尽可能长时间之间的时间段。 此外，条目标识符应重新分配给同一类型的另一个对象。 即一个特定的项标识符不应首先使用一条消息，然后与文件夹关联。
  
## <a name="see-also"></a>另请参阅



[MAPI 条目标识符](mapi-entry-identifiers.md)

