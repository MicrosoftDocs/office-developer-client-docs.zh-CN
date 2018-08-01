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
ms.openlocfilehash: ffdd1203316b2c80aba34c980745a0330ec19888
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776563"
---
# <a name="optional-features-for-address-book-providers"></a>通讯簿提供程序的可选功能

  
  
**适用于**： Outlook 
  
有许多地址簿提供程序的可选功能。 某些更常见实现的功能包括：
  
- 通过允许从一个容器添加到另一个提供商的容器的条目来充当外的提供程序。
    
- 通过向您容器之一从其他提供程序添加条目充当宿主提供程序。
    
- 高级搜索。
    
- 前缀滚动内容的表格。
    
- 支持通讯组列表。
    
- 事件通知的支持。
    
下表简要介绍这些可选功能和实现它们：
  
|**功能**|**如何实现**|
|:-----|:-----|
|提供用于创建收件人列表的邮件项的模板  <br/> |实现[IABLogon::GetOneOffTable](iablogon-getoneofftable.md)方法。 有关详细信息，请参阅[一次性表](one-off-tables.md)和[实现一次性表](implementing-one-off-tables.md)。  <br/> |
|到命名单元组收件人  <br/> |支持通讯组列表的属性，通过实现[IDistList: IMAPIContainer](idistlistimapicontainer.md)接口。  <br/> |
|用作外部地址簿提供程序，从而条目添加到容器中其他提供程序  <br/> | 支持的宿主提供程序中的数据绑定代码：  <br/>  消息用户和通讯组列表上支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。 有关详细信息，请参阅[地址簿标识符](address-book-identifiers.md)。  <br/>  实现[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)方法。 有关详细信息，请参阅[充当外的通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。  <br/> |
|通过从其他提供程序插入条目充当主机通讯簿提供程序  <br/> |支持将数据绑定到代码从外的提供程序通过调用[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)方法。 有关详细信息，请参阅[充当主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。  <br/> |
|前缀滚动  <br/> |支持容器内容表上的限制。 有关详细信息，请参阅[有关限制](about-restrictions.md)。  <br/> |
|高级搜索容器中  <br/> |在容器支持**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 的属性。 有关详细信息，请参阅[实现高级搜索](implementing-advanced-searching.md)。  <br/> |
|事件通知  <br/> |实现[IABLogon::Advise](iablogon-advise.md)和[IABLogon::Unadvise](iablogon-unadvise.md)方法。 有关详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)和[支持事件通知](supporting-event-notification.md)。  <br/> |
   
事件通知**IABLogon::Advise**方法将由调用 MAPI 客户端呼叫**IAddrBook::Advise**注册任一您容器上的通知消息用户或通讯组列表时。 但是，由于支持事件通知的操作是可选的您可以从这些方法返回 MAPI_E_NO_SUPPORT。 但是，MAPI 建议您至少支持内容表上的通知和鼓励您支持所有对象除_fnevSearchComplete_和_fnevCriticalError_事件的通知中添加值的类型。 
  

