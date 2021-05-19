---
title: 通讯簿提供程序的可选功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f1558259-7f0b-4731-80d2-88e51e203df0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9f5d8f0cd1b21f58e4e5c7d7ccd6cb19f3626c38
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414569"
---
# <a name="optional-features-for-address-book-providers"></a>通讯簿提供程序的可选功能

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿提供程序具有许多可选功能。 一些更常实现的功能包括：
  
- 通过允许将其中一个容器中的条目添加到另一个提供程序的容器中来充当外提供程序。
    
- 通过将另一个提供程序的条目添加到您的容器之一来充当主机提供程序。
    
- 高级搜索。
    
- 在内容表中滚动的前缀。
    
- 支持通讯组列表。
    
- 支持事件通知。
    
下表简要介绍了这些可选功能以及如何实现它们：
  
|**功能**|**如何实现**|
|:-----|:-----|
|提供用于创建邮件收件人列表条目的模板  <br/> |实现 [IABLogon：：GetOneOffTable](iablogon-getoneofftable.md) 方法。 有关详细信息，请参阅一键 [式表](one-off-tables.md) 和实现One-Off [表](implementing-one-off-tables.md)。  <br/> |
|将收件人分组到命名单位  <br/> |通过实现 [IDistList ： IMAPIContainer](idistlistimapicontainer.md) 接口支持通讯组列表的属性。  <br/> |
|通过允许将条目添加到另一个提供程序中的容器来充当外通讯簿提供程序  <br/> | 支持通过以下方法将代码绑定到主机提供程序中的数据：  <br/>  支持邮件 **PR_TEMPLATEID (** 列表) [PidTagTemplateid](pidtagtemplateid-canonical-property.md) 属性。 有关详细信息，请参阅 [通讯簿标识符](address-book-identifiers.md)。  <br/>  实现 [IABLogon：：OpenTemplateID](iablogon-opentemplateid.md) 方法。 有关详细信息，请参阅代理 [外通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。  <br/> |
|通过插入另一个提供商的条目来充当主机通讯簿提供程序  <br/> |支持通过调用 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md) 方法将数据绑定到来自外提供程序的代码。 有关详细信息，请参阅代理 [主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。  <br/> |
|前缀滚动  <br/> |支持对容器内容表的限制。 有关详细信息，请参阅关于 [限制](about-restrictions.md)。  <br/> |
|容器中的高级搜索  <br/> |支持 **PR_SEARCH (** [PidTagSearch)](pidtagsearch-canonical-property.md) 属性。 有关详细信息，请参阅 [实现高级搜索](implementing-advanced-searching.md)。  <br/> |
|事件通知  <br/> |实现 [IABLogon：：Advise](iablogon-advise.md) 和 [IABLogon：：Unadvise](iablogon-unadvise.md) 方法。 有关详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)[和支持事件通知](supporting-event-notification.md)。  <br/> |
   
对于事件通知，当客户端调用 **IAddrBook：：Advise** 以注册任何容器、邮件用户或通讯组列表上的通知时，MAPI 将调用 **IABLogon：：Advise** 方法。 但是，由于支持事件通知是可选的，因此可以从MAPI_E_NO_SUPPORT返回事件通知。 但是，MAPI 建议你至少支持有关内容表的通知，并鼓励你支持所有类型的对象通知  _，fnevSearchComplete_ 和  _fnevCriticalError_ 事件除外以添加值。 
  

