---
title: MAPI 服务提供程序
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6511e1b5-697e-4ed1-80af-aa8ca56fd045
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bb40891376ac511869ba157b675e53ee236b24ca
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409536"
---
# <a name="mapi-service-providers"></a>MAPI 服务提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
有三种常见类型的服务提供程序：
  
- 通讯簿提供程序。
    
- 邮件存储提供程序。
    
- 传输提供程序。
    
通讯簿和邮件存储提供程序有很多相似之处。 它们使用 MAPI 注册一个唯一标识符，用于构造其对象的条目标识符。 它们提供客户端可以访问和操作的对象和属性的层次结构。 对于容器对象，它们支持层次结构表和内容表。 它们支持在这些表上以及各个对象上（可选）的事件通知，以便客户端可以收到会话期间发生的更改的通知。 当操作变得很长时，它们可以显示进度指示器，以通知用户操作的状态。 客户端可以使用 [IAddrBook ： IMAPIProp](iaddrbookimapiprop.md) 和 [IMAPISession ： IUnknown](imapisessioniunknown.md) 接口间接通过 MAPI 与通讯簿和邮件存储提供程序进行通信，或者直接使用下表中的一个服务提供程序接口进行通信。 
  
|**通讯簿提供程序接口**|**邮件存储提供程序接口**|
|:-----|:-----|
|[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md) <br/> |[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) <br/> |
|[IDistList : IMAPIContainer](idistlistimapicontainer.md) <br/> |[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) <br/> |
|[IMailUser : IMAPIProp](imailuserimapiprop.md) <br/> |[IMessage : IMAPIProp](imessageimapiprop.md) <br/> |
| <br/> |[IAttach : IMAPIProp](iattachimapiprop.md) <br/> |
   
传输提供程序与通讯簿和邮件存储提供程序在与 MAPI 和客户端通信的方式上有所不同。 传输提供程序通常等待 MAPI 提示他们输入信息，而不是启动通信。 与其他提供程序不同，传输提供程序不支持客户端通常访问的各种对象和表。 但是，它们支持状态对象，就像所有服务提供程序一样，并且会将其属性发布到状态表中。 通讯簿和邮件存储提供程序调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md) 方法来注册用于构造其条目标识符的唯一标识符，而传输提供程序调用 [IXPLogon：：AddressTypes](ixplogon-addresstypes.md) 方法来注册唯一标识符，以及负责传递特定邮件的地址类型。 
  
您的服务提供商应具有三个头文件：一个公共头文件和两个内部文件。 使用公共头文件进行配置，并记录属性及其值。 包括其中一个内部头文件中所有必要的公共 MAPI 标头;此头文件应包含在所有服务提供程序源文件中。 使用另一个内部文件定义资源标识符。
  
通讯簿、邮件存储和传输提供程序执行以下任务：
  
- 提供入口点函数。 
    
- 提供提供程序和登录对象以处理登录和初始化。 
    
- 如果提供程序属于邮件服务，则提供邮件服务入口点功能。 
    
- 通过实现一个解决方案来支持属性表。
    
- 实现状态对象并支持状态表。 
    
- 处理关闭。
    
## <a name="see-also"></a>另请参阅



[MAPI 概念](mapi-concepts.md)

