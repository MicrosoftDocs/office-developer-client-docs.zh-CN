---
title: 注册服务提供程序唯一标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 964fceb4-8a1c-46c1-98e1-a325c9259f8b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bde7ff73f58c8809d2dd6467daea28461e7c6ef7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586268"
---
# <a name="registering-service-provider-unique-identifiers"></a>注册服务提供程序唯一标识符

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
通讯簿、 消息存储和传输提供程序使用的唯一标识符称为[MAPIUID](mapiuid.md)注册到服务的各种类型的对象。 **MAPIUID**是包含 GUID 的 16 字节标识符。 您可以使用以下过程创建**MAPIUID** : 
  
1. 定义常数。
    
2. 调用 Visual Studio*创建 GUID** 工具。 
    
例如，通讯簿提供程序可能在定义**MAPIUID**头文件中包含下列常量：
  
 `#define AB_UID_PROVIDER { 0Xe3, 0x3c, 0x67, 0xa0, \ 0xc8, 0x1f, 0x11, 0xce, \ 0xb2, 0xe4, 0x0, 0xaa, \ 0x0, 0x51, 0xe, 0x3b }`
  
 **如果您的提供商的地址簿或消息存储提供程序，注册 MAPIUID**
  
1. 调用[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)。
    
2. 注册的每次登录**MAPIUID**对象的实例化和创建每个条目标识符的**ab**成员的第一个 16 字节中包括此**MAPIUID** 。 MAPI 使用**MAPIUID**结构将对象与服务提供程序相关联。 当[IMAPISession::OpenEntry](imapisession-openentry.md)方法打开一个对象，MAPI 检查的项标识符的**MAPIUID**部分客户端呼叫时，将其与注册**MAPIUID**，以确定哪些登录对象匹配应收到打开请求。
    
3. MAPI 呼叫**IXPLogon::AddressTypes**方法时，如果您的提供商，传输注册一个或多个**MAPIUID**结构。 MAPI 使用由传输提供程序注册的**MAPIUID**结构分配用于邮件传递的责任。 
    
尽管服务提供商通常注册单个**MAPIUID**，您可以注册多个**MAPIUID**结构。 如果您的通讯簿或消息存储提供程序支持多个登录对象，可能是通过允许用户向其配置文件添加多个提供程序的实例，您可能希望实现的每个登录对象不同**MAPIUID** 。 有几个其他原因，以支持多个**MAPIUID**:
  
- 您必须支持多个提供程序的版本和条目标识符必须表示的适当版本。 分配每个版本不同**MAPIUID** 。 
    
- 您想要区分支持的对象的类型。 例如，通讯簿提供程序可能想要注册一个**MAPIUID**用于其消息的用户对象的项标识符和不同的**MAPIUID**用于通讯组列表。 
    
当存在多个同时处于活动状态的登录对象时，就应该具有为每个唯一**MAPIUID**结构。 这可增加与 MAPI 与匹配条目标识符与服务提供商并保存某些工作的准确性。 当每个登录对象具有自己的唯一标识符时，MAPI 都无法保证任何请求路由到登录对象可以处理由该对象。 登录对象共享**MAPIUID**结构，MAPI 将请求路由到由**MAPIUID**的第一个登录对象。 如果您的登录对象之一收到它无法处理，因为它无法处理的项标识符的请求，请将返回错误之前传递到下一步登录对象的请求。
  
## <a name="see-also"></a>另请参阅



[实现服务提供程序登录](implementing-service-provider-logon.md)

