---
title: MAPI 字符串属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 63d7360a-e3a3-4365-9d46-50df1c715bde
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9720b649eadecc73d84d98926674a1786796ba70
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431391"
---
# <a name="mapi-string-properties"></a>MAPI 字符串属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供了三种不同的属性类型来描述字符串属性：
  
PT_TSTRING
  
PT_STRING8
  
PT_UNICODE
  
字符串属性最常定义为PT_TSTRING。 该属性PT_TSTRING类型有条件地编译为其他字符串属性类型之一，具体取决于是否已定义 UNICODE 宏。 PT_STRING8 ANSI 格式描述 8 位以 null 结束的字符串;PT_UNICODE双字节以 null 结束的字符串。 
  
客户端或服务提供商，或者客户端和提供程序都可以选择支持 Unicode 字符串。 这不是必需的。 仅支持字符串的PT_STRING8可以与支持 Unicode 的提供程序一起操作，反之亦然。 为了启用此互操作性，客户端和服务提供商传递一个标志MAPI_UNICODE标志，以指示涉及字符串交换的方法支持 Unicode。 
  
例如，假设客户端支持 Unicode 并需要检索显示名称的名称。 将编译客户端的所有PT_TSTRING属性以键入PT_UNICODE。 当客户端调用文件夹 [的 IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索其 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性时，它会传递 MAPI_UNICODE 标志以请求以 Unicode 格式返回 显示名称 字符串。 
  
客户端和服务提供商需要知道，在方法调用中指定字符集只是一个请求。 支持一个或两个字符集由对象的实现者决定。 但是，鼓励服务提供商支持这两种字符集，因为它允许它们实现比仅支持一个字符集的提供程序更普遍分发。 
  
字符串属性可以像二进制属性（使用属性类型或属性类型的属性）一样PT_BINARY。 为了便于使用大型属性，MAPI 允许设置这些属性的服务提供商强制实施大小限制。 这些限制可能会有所不同，具体取决于：
  
- 属性是正在读取还是写入。
    
- 服务提供商如何实现 **IMAPIProp** 方法。 
    
- 运行时注意事项，如内存约束。
    
- 字符集转换问题。 
    
当在表的列集内使用字符串和二进制属性时，还可以对它们设置大小限制，因为有时不可能使所有大型属性的值都可见。 许多服务提供商将表中使用的大型字符串或二进制属性截断为 255 字节。 
  
当客户端调用对象的 **GetProps** 或 **SetProps** 方法以使用大型字符串或二进制属性时，由于属性大小，调用失败，该方法将返回错误值 MAPI_E_NOT_ENOUGH_MEMORY。 如果 **GetProps** 无法用于特定属性，则客户端可以通过调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 并请求 **IStream（** 将 IID_IStream 指定为接口标识符）进行恢复。 通过使用 **OpenProperty，** 客户端可以使用更适合使用大型属性的接口（如 **IStream）** 检索大型属性。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

