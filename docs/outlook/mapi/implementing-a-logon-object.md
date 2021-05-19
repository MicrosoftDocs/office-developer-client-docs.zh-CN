---
title: 实现登录对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 41e5c88c-d79d-4e9f-81f4-c4365cfaa15d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f9d77313012c2d133dc9352707ebc5e0c69c9973
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433043"
---
# <a name="implementing-a-logon-object"></a>实现登录对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个通讯簿、邮件存储和传输提供程序都会实例化登录对象，作为[实现 IABProvider：：Logon、IMSProvider：：Logon](iabprovider-logon.md)或[IXPProvider：：TransportLogon](ixpprovider-transportlogon.md)的一部分。 [](imsprovider-logon.md) 登录对象实现可帮助 MAPI 服务客户端请求的方法。 根据服务提供商的类型，您的登录对象将支持以下接口之一。 
  
|**登录对象接口**|**服务提供程序**|
|:-----|:-----|
|[IABLogon : IUnknown](iablogoniunknown.md) <br/> |通讯簿提供程序  <br/> |
|[IMSLogon : IUnknown](imslogoniunknown.md) <br/> |邮件存储提供程序  <br/> |
|[IXPLogon : IUnknown](ixplogoniunknown.md) <br/> |传输提供程序  <br/> |
   
通讯簿和邮件存储提供程序在登录对象中实现以下功能：
  
- 支持事件通知 (**Advise** 和 **Unadvise** 方法) 。 有关事件通知的概述，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。 有关在登录对象中支持通知的信息，请参阅 [支持事件通知](supporting-event-notification.md)。 
    
- **CompareEntryIDs** (的条目标识符) 。 有关条目标识符的常规信息，请参阅 [MAPI 条目标识符](mapi-entry-identifiers.md)。 有关在登录对象的 **CompareEntryIDs** 方法中比较条目标识符的信息，请参阅S [supporting Object Access and Comparison。](supporting-object-access-and-comparison.md)
    
- 使用 **GetLastError** 方法 (访问其他) 。 有关处理 MAPI 中的错误的详细信息，请参阅 [MAPI 中的错误处理](error-handling-in-mapi.md)。 
    
- 使用 **OpenEntry** 方法访问由服务提供商 (的对象) 。 有关详细信息，请参阅支持 [对象访问和比较](supporting-object-access-and-comparison.md)。
    
- 使用 **OpenStatusEntry** 方法 (访问状态) 。 有关状态对象的一般信息，请参阅 [MAPI Status Objects](mapi-status-objects.md)。 有关实现状态对象的特定信息，请参阅 [状态对象实现](status-object-implementation.md)。
    
- 使用 Logoff 方法 **(注销**) 。 有关详细信息，请参阅 [关闭服务提供程序](shutting-down-a-service-provider.md)。
    
如果您的提供程序是通讯簿提供程序，则还将实现以下方法和关联功能：
  
- [IABLogon：：GetOneOffTable，](iablogon-getoneofftable.md) 用于提供支持创建新收件人的模板列表。 有关详细信息，请参阅一键 [式表](one-off-tables.md) 或 [实现提供程序One-Off表](implementing-a-provider-one-off-table.md)。
    
- [IABLogon：：OpenTemplateID，](iablogon-opentemplateid.md) 用于提供对数据驻留在主机通讯簿提供程序中的收件人的实现的访问。 有关详细信息，请参阅代理 [外通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。 
    
- [IABLogon：:P repareRecips](iablogon-preparerecips.md) 以确保适当的属性可用于收件人列表中的所有收件人。 有关详细信息，请参阅 [IABLogon：:P repareRecips](iablogon-preparerecips.md)。 
    
实现 [IXPLogon ： IUnknown](ixplogoniunknown.md)的传输提供程序的登录对象与其他类型的服务提供商实现的登录对象完全不同。 它只有两个与其他登录对象共同的功能：通过 [IXPLogon：：OpenStatusEntry](ixplogon-openstatusentry.md) 方法访问状态对象，以及通过 [IXPLogon：：TransportLogoff](ixplogon-transportlogoff.md) 方法执行注销操作。 传输提供程序在登录对象中实现以下唯一功能： 
  
- 使用 [IXPLogon：：AddressTypes](ixplogon-addresstypes.md) (注册地址类型) 。 有关注册地址类型的信息，请参阅传输提供程序和 [MAPI 后台处理程序操作模型](transport-provider-and-mapi-spooler-operational-model.md)。
    
- 控制邮件传输 ([IXPLogon：：StartMessage、IXPLogon：：EndMessage](ixplogon-startmessage.md)和[IXPLogon：：SubmitMessage](ixplogon-submitmessage.md)) 。 [](ixplogon-endmessage.md) 有关详细信息，请参阅邮件 [接收模型](message-reception-model.md)、与 [MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)和 [邮件提交模型](message-submission-model.md)。
    
- [IXPLogon (：：ValidateState 方法的内部](ixplogon-validatestate.md)) 。 
    
- 使用 [IXPLogon：：FlushQueues](ixplogon-flushqueues.md) (按需下载或上载) 。 有关详细信息，请参阅实现 [FlushQueues 方法](implementing-the-flushqueues-method.md)。
    
- 使用 ([IXPLogon：:P方法](ixplogon-poll.md) 查询挂起) 。 有关详细信息，请参阅邮件 [接收模型](message-reception-model.md)。
    
- [IXPLogon (：：Idle 方法的空闲](ixplogon-idle.md)状态) 。 
    
- 与 [IXPLogon：：TransportNotify](ixplogon-transportnotify.md) (MAPI 后台处理程序的) 。 
    
## <a name="see-also"></a>另请参阅



[实现服务提供程序登录](implementing-service-provider-logon.md)

