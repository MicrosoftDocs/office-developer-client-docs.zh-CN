---
title: MAPI 服务提供商
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6511e1b5-697e-4ed1-80af-aa8ca56fd045
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1f931382e790da13e7d4a746e286d9dc176b7b6b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571904"
---
# <a name="mapi-service-providers"></a>MAPI 服务提供商

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
有三种常见类型的服务提供商：
  
- 通讯簿提供程序。
    
- 消息存储提供程序。
    
- 传输提供程序。
    
地址簿和消息存储提供程序具有许多相似之处。 他们与他们用于构建其对象的项标识符的 MAPI 注册的唯一标识符。 它们提供对象和属性的客户端可以访问和操作层次的结构。 对于其容器对象，它们支持的层次结构表和内容表。 以便可以在会话过程中发生的更改的通知客户端，它们支持了对这些表和 （可选） 在单个对象的事件通知。 操作长时，它们可以显示进度指示器，告知用户操作的状态。 客户端可以使用与通信地址簿和消息存储提供程序任一间接到 MAPI [IAddrBook: IMAPIProp](iaddrbookimapiprop.md)和[IMAPISession: IUnknown](imapisessioniunknown.md)接口或直接通过使用中的服务提供程序接口之一下表。 
  
|**通讯簿提供程序接口**|**消息存储提供程序接口**|
|:-----|:-----|
|[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md) <br/> |[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) <br/> |
|[IDistList : IMAPIContainer](idistlistimapicontainer.md) <br/> |[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) <br/> |
|[IMailUser : IMAPIProp](imailuserimapiprop.md) <br/> |[IMessage : IMAPIProp](imessageimapiprop.md) <br/> |
| <br/> |[IAttach : IMAPIProp](iattachimapiprop.md) <br/> |
   
传输提供程序与他们通信与 MAPI 和客户端的方式的地址簿和消息存储提供程序不同。 传输提供程序通常等待 MAPI 提示他们的信息，而不是交流。 与其他提供程序，不同传输提供程序不支持的各种对象和通常由客户端访问的表。 但是，它们支持一个状态对象中，在执行所有服务提供程序，并在状态表中发布其属性。 传输提供程序通讯簿和消息存储提供程序调用[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法以注册用于构建它们的项标识符的唯一标识符，而呼叫[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法假定责任特定邮件的传递注册唯一标识符，以及地址类型。 
  
服务提供商应具有三个标头文件： 一个公共头文件和两个内部文件。 配置和记录属性以及它们的值，请使用公共头文件。 内部标头文件中包含的所有必要公共 MAPI 标题;此头文件应包含在所有服务提供程序源文件。 使用其他内部文件定义资源标识符。
  
通讯簿、 消息存储和传输提供程序执行以下任务：
  
- 提供入口点函数。 
    
- 提供一个提供程序和登录对象，以处理登录和初始化。 
    
- 如果提供程序属于邮件服务，提供邮件服务入口点函数。 
    
- 通过实现属性表中支持的配置。
    
- 实现状态对象和支持状态表。 
    
- 关闭的句柄。
    
## <a name="see-also"></a>另请参阅



[MAPI 概念](mapi-concepts.md)

