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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332842"
---
# <a name="implementing-a-logon-object"></a>实现登录对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个通讯簿、邮件存储和传输提供程序将登录对象实例化为其 IABProvider 实现的一部分[:: logon](iabprovider-logon.md)、 [IMSProvider:: logon](imsprovider-logon.md)或[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)。 登录对象实现帮助 MAPI 服务客户端请求的方法。 根据您的服务提供程序的类型, 您的登录对象将支持下列接口之一。 
  
|**登录对象接口**|**服务提供程序**|
|:-----|:-----|
|[IABLogon : IUnknown](iablogoniunknown.md) <br/> |通讯簿提供程序  <br/> |
|[IMSLogon : IUnknown](imslogoniunknown.md) <br/> |邮件存储区提供程序  <br/> |
|[IXPLogon : IUnknown](ixplogoniunknown.md) <br/> |传输提供程序  <br/> |
   
通讯簿和邮件存储提供程序在其登录对象中实现以下功能:
  
- 支持事件通知 (**建议**和**Unadvise**方法)。 有关事件通知的概述, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 有关登录对象中支持通知的详细信息, 请参阅[支持事件通知](supporting-event-notification.md)。 
    
- 条目标识符比较 (**CompareEntryIDs**方法)。 有关条目标识符的一般信息, 请参阅[MAPI 条目标识符](mapi-entry-identifiers.md)。 有关在登录对象的**CompareEntryIDs**方法中比较条目标识符的详细信息, 请参阅[支持对象访问和比较](supporting-object-access-and-comparison.md)。
    
- 对其他错误信息 (**GetLastError**方法) 的访问权限。 有关处理 mapi 中的错误的详细信息, 请参阅[mapi 中的错误处理](error-handling-in-mapi.md)。 
    
- 对服务提供程序 (**OpenEntry**方法) 实现的对象的访问权限。 有关详细信息, 请参阅[支持对象访问和比较](supporting-object-access-and-comparison.md)。
    
- 对 status 对象 (**OpenStatusEntry**方法) 的访问权限。 有关 status 对象的一般信息, 请参阅[MAPI 状态对象](mapi-status-objects.md)。 有关实现 status 对象的具体信息, 请参阅[status object 实现](status-object-implementation.md)。
    
- 注销过程 (**注销**方法)。 有关详细信息, 请参阅[关闭服务提供程序](shutting-down-a-service-provider.md)。
    
如果您的提供商是通讯簿提供商, 您还将实现以下方法和相关功能:
  
- [IABLogon:: GetOneOffTable](iablogon-getoneofftable.md)提供创建新收件人所支持的模板的列表。 有关详细信息, 请参阅[一次性表](one-off-tables.md)或[实现提供程序一次性表](implementing-a-provider-one-off-table.md)。
    
- [IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)提供对其数据驻留在主机通讯簿提供程序中的收件人的实现的访问权限。 有关详细信息, 请参阅[充当外部通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。 
    
- [IABLogon::P reparerecips](iablogon-preparerecips.md) , 以确保收件人列表中的所有收件人都可以使用相应的属性。 有关详细信息, 请参阅[IABLogon::P reparerecips](iablogon-preparerecips.md)。 
    
传输提供程序的登录对象 (实现[IXPLogon: IUnknown](ixplogoniunknown.md)) 与其他类型的服务提供程序所实现的登录对象非常不同。 它仅具有与其他登录对象共有的两个功能: 通过[IXPLogon:: OpenStatusEntry](ixplogon-openstatusentry.md)方法访问 status 对象和通过[IXPLogon:: TransportLogoff](ixplogon-transportlogoff.md)方法进行的注销操作。 传输提供程序在其登录对象中实现以下独特功能: 
  
- 地址类型注册 ([IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法)。 有关注册地址类型的详细信息, 请参阅[传输提供程序和 MAPI 后台处理程序操作模型](transport-provider-and-mapi-spooler-operational-model.md)。
    
- 控制邮件传输 ([IXPLogon:: StartMessage](ixplogon-startmessage.md)、 [IXPLogon:: EndMessage](ixplogon-endmessage.md)和[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md)方法)。 有关详细信息, 请参阅[邮件接收模型](message-reception-model.md)、[与 MAPI 后台处理程序的交互](interacting-with-the-mapi-spooler.md)和[邮件提交模型](message-submission-model.md)。
    
- 内部状态验证 ([IXPLogon:: ValidateState](ixplogon-validatestate.md)方法)。 
    
- 能够按需下载或上传邮件 ([IXPLogon:: FlushQueues](ixplogon-flushqueues.md)方法)。 有关详细信息, 请参阅[实现 FlushQueues 方法](implementing-the-flushqueues-method.md)。
    
- 能够查询挂起的邮件 ([IXPLogon::P oll](ixplogon-poll.md)方法)。 有关详细信息, 请参阅[邮件接收模型](message-reception-model.md)。
    
- 空闲状态检测 ([IXPLogon:: Idle](ixplogon-idle.md)方法)。 
    
- 与 MAPI 后台处理程序的交互 ([IXPLogon:: TransportNotify](ixplogon-transportnotify.md)方法)。 
    
## <a name="see-also"></a>另请参阅



[实现服务提供程序登录](implementing-service-provider-logon.md)

