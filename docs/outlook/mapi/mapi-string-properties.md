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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309518"
---
# <a name="mapi-string-properties"></a>MAPI 字符串属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供了三种不同的属性类型来描述字符串属性:
  
PT_TSTRING
  
PT_STRING8
  
PT_UNICODE
  
字符串属性最常定义为 PT_TSTRING。 PT_TSTRING 属性类型有条件地编译为其他字符串属性类型之一, 具体取决于是否已定义 UNICODE 宏。 PT_STRING8 介绍了 ANSI 格式的8位 null 结尾字符字符串;PT_UNICODE 描述双字节以 null 结尾的字符串。 
  
客户端或服务提供商, 或者客户端和提供程序都可以选择支持 Unicode 字符字符串。 这不是必需的。 仅支持 PT_STRING8 字符串的客户端可以使用支持 Unicode 的提供程序运行, 反之亦然。 若要启用此互操作性, 客户端和服务提供程序将传递一个标志, 即 MAPI_UNICODE 标志, 以指示涉及交换字符字符串的方法中支持 UNICODE。 
  
例如, 假设客户端支持 Unicode 并需要检索文件夹的显示名称。 将所有客户端的 PT_TSTRING 属性编译为 PT_UNICODE 类型。 当客户端调用文件夹的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性时, 它会传递 MAPI_UNICODE 标志以请求以 UNICODE 格式返回显示名称字符串。. 
  
客户端和服务提供商需要注意, 在方法调用中指定字符集只是一个请求。 支持一个或两个字符集由对象的实施者负责。 但是, 建议服务提供商支持这两个字符集, 因为它允许他们实现比仅支持一个集的提供程序更广泛的分布。 
  
对于 binary 属性 (使用属性类型 PT_BINARY 的属性), 字符串属性可能会变得非常大。 为了简化大型属性的使用, MAPI 允许服务提供程序设置这些属性来强制大小限制。 这些限制可能会有所不同, 具体取决于:
  
- 是否正在读取或写入属性。
    
- 服务提供程序如何实现**IMAPIProp**方法。 
    
- 运行时注意事项, 如内存约束。
    
- 字符集转换问题。 
    
在表的列集中使用时, 还可以对 string 和 binary 属性放置大小限制, 因为有时无法使所有大型属性的值可见。 许多服务提供程序会将在表中使用的大型字符串或二进制属性截断为255字节。 
  
当客户端调用对象的**GetProps**或**SetProps**方法来处理大型字符串或二进制属性, 并且由于属性大小而导致调用失败时, 该方法将返回错误值 MAPI_E_NOT_ENOUGH_MEMORY。 如果它是特定属性失败的**GetProps** , 客户端可以通过将 IID_IStream 指定为接口标识符, 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)并请求**IStream**进行访问来进行恢复。 通过使用**OpenProperty**, 客户端可以使用接口 (如**IStream** ) 检索大型属性, 后者更适合处理大型属性。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

