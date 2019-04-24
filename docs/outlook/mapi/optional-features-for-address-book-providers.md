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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348564"
---
# <a name="optional-features-for-address-book-providers"></a>通讯簿提供程序的可选功能

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿提供程序有许多可选功能。 一些更常用的一些功能包括:
  
- 通过允许将某个容器中的项添加到另一个提供程序的容器, 充当外部提供程序。
    
- 通过向某个容器添加其他提供程序中的项来充当主机提供程序。
    
- 高级搜索。
    
- 通过内容表滚动的前缀。
    
- 对通讯组列表的支持。
    
- 支持事件通知。
    
下表简要介绍了这些可选功能以及如何实现这些功能:
  
|**功能**|**如何实现**|
|:-----|:-----|
|提供用于创建邮件收件人列表条目的模板  <br/> |实现[IABLogon:: GetOneOffTable](iablogon-getoneofftable.md)方法。 有关详细信息, 请参阅[一次性表](one-off-tables.md)和[实现一次性表](implementing-one-off-tables.md)。  <br/> |
|将收件人分组为命名的单位  <br/> |通过实现[IDistList: IMAPIContainer](idistlistimapicontainer.md)接口, 支持通讯组列表的属性。  <br/> |
|通过允许将条目添加到另一个提供程序中的容器来充当外部通讯簿提供程序  <br/> | 通过以下方式支持向主机提供程序中的数据绑定代码:  <br/>  支持邮件用户和通讯组列表上的**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。 有关详细信息, 请参阅[通讯簿标识符](address-book-identifiers.md)。  <br/>  实现[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)方法。 有关详细信息, 请参阅[充当外部通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。  <br/> |
|通过从另一个提供程序插入条目充当主机通讯簿提供程序  <br/> |通过调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)方法, 支持将数据绑定到来自外部提供程序的代码。 有关详细信息, 请参阅[充当主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。  <br/> |
|前缀滚动  <br/> |支持对容器内容表的限制。 有关详细信息, 请参阅[关于限制](about-restrictions.md)。  <br/> |
|容器中的高级搜索  <br/> |支持容器上的**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 属性。 有关详细信息, 请参阅[实施高级搜索](implementing-advanced-searching.md)。  <br/> |
|事件通知  <br/> |实现[IABLogon:: Advise](iablogon-advise.md)和[IABLogon:: Unadvise](iablogon-unadvise.md)方法。 有关详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[支持事件通知](supporting-event-notification.md)。  <br/> |
   
对于事件通知, 当客户端调用**IAddrBook:: 建议**在任何一个容器、邮件用户或通讯组列表中注册通知时, MAPI 将调用**IABLogon:: advise**方法。 但是, 由于支持事件通知是可选的, 因此可以从这些方法返回 MAPI_E_NO_SUPPORT。 但是, MAPI 确实建议您至少支持对内容表的通知, 并鼓励您支持所有类型的对象通知, 除了_fnevSearchComplete_和_fnevCriticalError_事件以添加值之外。 
  

