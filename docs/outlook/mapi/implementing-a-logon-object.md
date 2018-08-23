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
ms.openlocfilehash: 99a8473abf01467c534c0ea829e342fa46489e99
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568019"
---
# <a name="implementing-a-logon-object"></a>实现登录对象

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
每个通讯簿、 消息存储和传输提供程序实例化的[IABProvider::Logon](iabprovider-logon.md)、 [IMSProvider::Logon](imsprovider-logon.md)，或[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)其实现一部分登录对象。 登录对象实现帮助 MAPI 服务客户端请求的方法。 根据您的服务提供商的类型，登录对象将支持以下接口之一。 
  
|**登录对象接口**|**服务提供商**|
|:-----|:-----|
|[IABLogon : IUnknown](iablogoniunknown.md) <br/> |通讯簿提供程序  <br/> |
|[IMSLogon : IUnknown](imslogoniunknown.md) <br/> |消息存储提供程序  <br/> |
|[IXPLogon : IUnknown](ixplogoniunknown.md) <br/> |传输提供程序  <br/> |
   
通讯簿和消息存储提供程序实现以下功能在其登录对象中：
  
- 事件通知 （**Advise**和**Unadvise**方法） 的支持。 事件通知的概述，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 有关登录对象中支持通知的详细信息，请参阅[支持的事件通知](supporting-event-notification.md)。 
    
- 项标识符比较 （**CompareEntryIDs**方法）。 有关条目标识符的常规信息，请参阅[MAPI 条目标识符](mapi-entry-identifiers.md)。 有关比较登录对象的**CompareEntryIDs**方法中的项标识符的详细信息，请参阅[支持对象访问和比较](supporting-object-access-and-comparison.md)。
    
- 访问其他错误信息 （**GetLastError**方法）。 有关处理 MAPI 中的错误的详细信息，请参阅[MAPI 中的错误处理](error-handling-in-mapi.md)。 
    
- 实现由服务提供商 （**OpenEntry**方法） 的对象的访问。 有关详细信息，请参阅[支持对象访问和比较](supporting-object-access-and-comparison.md)。
    
- 访问状态对象 （**OpenStatusEntry**方法）。 有关状态的对象的常规信息，请参阅[MAPI 状态对象](mapi-status-objects.md)。 有关实现状态对象的特定信息，请参阅[状态对象实现](status-object-implementation.md)。
    
- 注销过程 （**Logoff**方法）。 有关详细信息，请参阅[关机的情况下服务 Provider](shutting-down-a-service-provider.md)。
    
如果您的提供商的地址簿提供程序，您将实现以下方法和关联的功能：
  
- [IABLogon::GetOneOffTable](iablogon-getoneofftable.md)来提供支持用于创建新的收件人的模板的列表。 有关详细信息，请参阅[一次性表](one-off-tables.md)或[实现提供程序一次性表](implementing-a-provider-one-off-table.md)。
    
- [IABLogon::OpenTemplateID](iablogon-opentemplateid.md)以提供对收件人的实现访问其数据位于主机通讯簿提供程序。 有关详细信息，请参阅[充当外的通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。 
    
- [IABLogon::PrepareRecips](iablogon-preparerecips.md) ，以确保的相应属性可用于所有收件人列表中的收件人。 有关详细信息，请参阅[IABLogon::PrepareRecips](iablogon-preparerecips.md)。 
    
传输提供程序的登录对象，实现[IXPLogon: IUnknown](ixplogoniunknown.md)，则由其他类型的服务提供商实现的登录对象从完全不同。 它具有共同之处的其他登录对象只有两个功能： 访问[IXPLogon::OpenStatusEntry](ixplogon-openstatusentry.md)方法通过状态对象和通过[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md)方法注销操作。 传输提供程序在其登录对象中实现以下唯一功能： 
  
- 注册地址类型 （[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法）。 有关注册地址类型的详细信息，请参阅[传输提供程序和 MAPI 后台处理程序操作模型](transport-provider-and-mapi-spooler-operational-model.md)。
    
- 邮件传输 （[IXPLogon::StartMessage](ixplogon-startmessage.md)、 [IXPLogon::EndMessage](ixplogon-endmessage.md)和[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)方法） 的控件。 有关详细信息，请参阅[消息接收模型](message-reception-model.md)、[与 MAPI 后台处理程序的交互](interacting-with-the-mapi-spooler.md)和[消息提交模型](message-submission-model.md)。
    
- 内部状态验证 （[IXPLogon::ValidateState](ixplogon-validatestate.md)方法）。 
    
- 若要下载或上载按需型 （[IXPLogon::FlushQueues](ixplogon-flushqueues.md)方法） 的消息的功能。 有关详细信息，请参阅[实现 FlushQueues 方法](implementing-the-flushqueues-method.md)。
    
- 待处理的邮件 （[IXPLogon::Poll](ixplogon-poll.md)方法） 查询的能力。 有关详细信息，请参阅[消息接收模型](message-reception-model.md)。
    
- 空闲状态检测 （[IXPLogon::Idle](ixplogon-idle.md)方法）。 
    
- 与 MAPI 后台处理程序 （[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法） 进行交互。 
    
## <a name="see-also"></a>另请参阅



[实现服务提供程序登录](implementing-service-provider-logon.md)

