---
title: MAPI 字符串属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 63d7360a-e3a3-4365-9d46-50df1c715bde
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3e16a373ec35696f6d1a8ccc52263a1cf8570cfc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572324"
---
# <a name="mapi-string-properties"></a>MAPI 字符串属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 提供了三种不同的属性类型来描述字符串属性：
  
PT_TSTRING
  
PT_STRING8
  
PT_UNICODE
  
字符串属性最常被定义为 PT_TSTRING。 为其他字符串属性类型之一，具体取决于是否已定义 UNICODE 宏有条件地编译 PT_TSTRING 属性类型。 PT_STRING8 描述 ANSI 格式; 8 位 null 结尾的字符串字符串PT_UNICODE 描述双字节 null 结尾字符的字符串。 
  
通过客户端或服务提供商，或客户端和提供程序可以选择支持的 Unicode 字符串。 不需要。 支持仅 PT_STRING8 字符串的客户端可以运行的提供程序支持 Unicode，反之亦然。 若要启用此互操作性，客户端和服务提供商，请传递标志，MAPI_UNICODE 标志，以指示 Unicode 支持中涉及的字符串交换的方法。 
  
例如，假设客户端中支持 Unicode，并且需要检索文件夹的显示名称。 编译的所有客户端的 PT_TSTRING 属性键入 PT_UNICODE。 当客户端调用该文件夹的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性时，它将传递 MAPI_UNICODE 标志以请求返回的显示名称字符串以 Unicode 格式. 
  
客户端和服务提供商需要注意的指定在方法调用中的字符集是仅请求。 支持一个或两个字符设置为最多为对象的实施。 但是，建议以支持两个字符集，因为它允许他们能够实现更广泛分发比支持只有一组提供程序的服务提供商。 
  
字符串属性可以增长得很大，如可以二进制属性 — 使用属性的属性键入 PT_BINARY。 为了便于使用大型属性，MAPI 允许服务提供商设置这些属性强制实施大小限制。 这些限制可以有所不同，具体取决于：
  
- 是否正在属性读取或写入。
    
- 如何服务提供商实现**IMAPIProp**方法。 
    
- 运行时的注意事项，例如内存限制。
    
- 字符集转换问题。 
    
此外可以在字符串上放置大小限制，因为它是有时可能使大型属性的值的所有可见时使用的列中的二进制属性设置的表。 许多服务提供商截断大的字符串或 255 个字节的表中使用的二进制属性。 
  
当客户端调用对象的**GetProps**或**SetProps**方法来处理大的字符串或二进制属性，并调用将失败，因为属性大小时，该方法将返回错误值 MAPI_E_NOT_ENOUGH_MEMORY。 如果是**GetProps**出现故障的特定属性，可以通过调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)并通过接口标识指定 IID_IStream 请求访问**IStream**恢复客户端。 使用**OpenProperty**，客户端可以检索使用如是更适合使用大型属性的**IStream**接口的大型属性。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

