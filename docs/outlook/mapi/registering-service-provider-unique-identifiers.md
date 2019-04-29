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
  
通讯簿、邮件存储和传输提供程序使用唯一标识符 (称为 " [MAPIUID](mapiuid.md) ") 来注册各种类型的服务对象。 **MAPIUID**是一个包含 GUID 的16字节标识符。 您可以使用以下过程创建**MAPIUID** : 
  
1. 定义一个常量。
    
2. 调用 Visual Studio*创建 GUID** 工具。 
    
例如, 通讯簿提供程序可能在头文件中包含以下常量以定义**MAPIUID**:
  
 `#define AB_UID_PROVIDER { 0Xe3, 0x3c, 0x67, 0xa0, \ 0xc8, 0x1f, 0x11, 0xce, \ 0xb2, 0xe4, 0x0, 0xaa, \ 0x0, 0x51, 0xe, 0x3b }`
  
 **如果提供商是通讯簿或邮件存储提供程序, 则注册 MAPIUID**
  
1. 调用[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md)。
    
2. 为您实例化的每个登录对象注册**MAPIUID** , 并在您创建的每个条目标识符的**ab**成员的前16个字节中包含此**MAPIUID** 。 MAPI 使用**MAPIUID**结构将对象与服务提供程序相关联。 当客户端调用[IMAPISession:: OpenEntry](imapisession-openentry.md)方法打开一个对象时, MAPI 会检查条目标识符的**MAPIUID**部分, 使其与注册的**MAPIUID**相匹配, 以确定哪个登录对象应接收打开的申请.
    
3. 如果您的提供商是传输, 则在 MAPI 调用您的**IXPLogon:: AddressTypes**方法时, 请注册一个或多个**MAPIUID**结构。 MAPI 使用由传输提供程序注册的**MAPIUID**结构来分配邮件传递的责任。 
    
尽管服务提供商通常注册一个**MAPIUID**, 但您可以注册多个**MAPIUID**结构。 如果您的通讯簿或邮件存储提供程序支持多个登录对象 (可能是允许用户将提供程序的多个实例添加到其配置文件中), 则可能需要为每个登录对象实现一个不同的**MAPIUID** 。 支持多个**MAPIUID**的其他一些原因如下:
  
- 您必须支持多个版本的提供程序, 条目标识符必须代表适当的版本。 为每个版本分配不同的**MAPIUID** 。 
    
- 您想区分所支持的对象类型。 例如, 通讯簿提供商可能希望注册一个**MAPIUID**以在其邮件用户对象的条目标识符中使用, 并使用不同的**MAPIUID**来用于通讯组列表。 
    
当存在并发活动的多个登录对象时, 有必要为每个对象提供唯一的**MAPIUID**结构。 这提高了 MAPI 将条目标识符与服务提供程序相匹配并保存一些工作的准确性。 当每个登录对象都有其自己的唯一标识符时, MAPI 可以保证其路由到登录对象的任何请求都可以由该对象处理。 当登录对象共享**MAPIUID**结构时, MAPI 会将请求路由到**MAPIUID**标识的第一个登录对象。 如果你的某个登录对象收到由于未处理条目标识符而无法处理的请求, 请在返回错误之前将请求传递到下一个登录对象。
  
## <a name="see-also"></a>另请参阅



[实现服务提供程序登录](implementing-service-provider-logon.md)

