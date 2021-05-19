---
title: 注册服务提供程序唯一标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 964fceb4-8a1c-46c1-98e1-a325c9259f8b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9f4acbb06f85a88a6c057da263ae95e09f72e0bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410173"
---
# <a name="registering-service-provider-unique-identifiers"></a>注册服务提供程序唯一标识符

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿、邮件存储和传输提供程序使用称为 [MAPIUID](mapiuid.md) 的唯一标识符注册到各种类型的服务对象。 **MAPIUID** 是包含 GUID 的 16 字节标识符。 可以使用以下 **过程创建 MAPIUID：** 
  
1. 定义一个常量。
    
2. 调用Visual Studio *GUID** 工具。 
    
例如，通讯簿提供程序可能将以下常量包括在头文件中以定义 **MAPIUID**：
  
 `#define AB_UID_PROVIDER { 0Xe3, 0x3c, 0x67, 0xa0, \ 0xc8, 0x1f, 0x11, 0xce, \ 0xb2, 0xe4, 0x0, 0xaa, \ 0x0, 0x51, 0xe, 0x3b }`
  
 **如果提供程序是通讯簿或邮件存储提供程序，则注册 MAPIUID**
  
1. 调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md)。
    
2. 为实例化的每个登录对象注册 **MAPIUID，** 并在此创建的每个条目标识符的 **ab** 成员前 16 个字节中包括此 **MAPIUID。** MAPI 使用 **MAPIUID** 结构将对象与服务提供商关联。 当客户端调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 方法打开对象时，MAPI 将检查条目标识符的 **MAPIUID** 部分，并针对注册的 **MAPIUID** 进行匹配，以确定哪个登录对象应接收打开的请求。
    
3. 如果提供程序是传输提供程序，请在 MAPI 调用 **IXPLogon：：AddressTypes** 方法时注册一个或多个 **MAPIUID** 结构。 MAPI 使用由传输提供程序注册的 **MAPIUID** 结构来分配邮件传递的责任。 
    
虽然服务提供商通常注册一个 **MAPIUID，** 但您可以注册多个 **MAPIUID** 结构。 如果通讯簿或邮件存储提供程序支持多个登录对象（可能允许用户将提供程序的多个实例添加到其配置文件中，则您可能希望针对每个登录对象实现不同的 **MAPIUID）。** 支持多个 **MAPIUID** 的其他一些原因如下：
  
- 必须支持多个版本的提供程序，并且条目标识符必须表示相应的版本。 为每个版本分配不同的 **MAPIUID。** 
    
- 要区分支持的对象类型。 例如，通讯簿提供程序可能想要注册一 **个 MAPIUID** 以用于其邮件用户对象的条目标识符和另一个 **MAPIUID** 以用于通讯组列表。 
    
当有多个同时处于活动状态的登录对象时，每个对象具有唯一 **的 MAPIUID** 结构是有意义的。 这将提高 MAPI 与服务提供程序的条目标识符匹配并节省一些工作的准确性。 当每个登录对象都有其自己的唯一标识符时，MAPI 可以保证它路由到登录对象的任何请求都可以通过该对象进行处理。 当登录对象共享 **MAPIUID 结构时，MAPI** 将请求路由到 **MAPIUID** 标识的第一个登录对象。 如果其中一个登录对象收到由于不处理条目标识符而无法处理的请求，则先将请求传递到下一个登录对象，然后再返回错误。
  
## <a name="see-also"></a>另请参阅



[实现服务提供程序登录](implementing-service-provider-logon.md)

