---
title: 充当主机通讯簿提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f06a1034-ee49-4a09-831e-9752713228a8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 202d4b4391de7553e39e50dc527df5502ebcefb3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406463"
---
# <a name="acting-as-a-host-address-book-provider"></a>充当主机通讯簿提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
宿主提供程序是一个通讯簿提供程序，其中包含来自其容器中的其他提供程序的收件人，并且依靠其他提供程序的收件人实现来部分控制其维护。 宿主提供商使用这些外收件人的模板标识符，将这些收件人的数据绑定到该外提供程序中的代码。 当提供程序检索收件人的 **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性，并传递给 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md)的调用时，将启动此绑定过程。 
  
当提供程序调用 **IMAPISupport：：OpenTemplateID** 时，MAPI 与模板标识符中的 **MAPIUID** 与提供程序注册的 **MAPIUID** 匹配，并调用提供程序的 [IABLogon：：OpenTemplateID](iablogon-opentemplateid.md) 方法。 该外提供程序可能会返回一个指针，指向提供程序的属性对象、它自己的属性对象实现或包装提供程序对象的实现。 返回的指针放置在  _lppMAPIPropNew_ 参数的内容中。 
  
您的提供程序可以选择是否调用 **IMAPISupport：：OpenTemplateID，FILL_ENTRY** 设置。 创建收件人时或在提供程序刷新收件人属性后经过很长时间后设置此标志。 该标志的FILL_ENTRY是使提供程序中的收件人与原始收件人保持同步。 实现此类型的同步计划可提高性能。 
  
 **保持外收件人同步**
  
1. 确定定期更新的适当间隔。 
    
2. 每次调用 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md)的时间戳。 
    
3. 根据自上次调用以来的到期时间，评估是否需要执行完整更新。 如果需要完整更新，请调用具有 FILL_ENTRY 标志的 **IMAPISupport：：OpenTemplateID。** 如果没有必要，请不要在调用上设置 标志。 
    
当客户端对复制的收件人的属性之一提出请求时，您的提供商可以选择是处理请求本身，还是使用由外提供程序提供的代码。 除了 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)之外，你的提供程序可以预期外提供商会截取大部分（如果不是全部 **）IMAPIProp** 调用。 始终将调用 **OpenProperty** PR_DETAILS_TABLE ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性转发到提供程序。 
  
 **访问模板标识符代码**
  
1. 打开收件人并调用其[IMAPIProp：：GetProps](imapiprop-getprops.md)方法来检索PR_TEMPLATEID ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。 如果 **GetProps** 因PR_TEMPLATEID不可用而失败，则外提供程序不支持此收件人的模板标识符和相关代码。 您的提供商将需要使用其收件人实现进行所有维护。 
    
2. 如果从 **GetProps** 返回模板标识符，请传递该标识符，并通过调用 **IMAPISupport：：OpenTemplateID** 方法，将指针传递给收件人的 **IMAPIProp** 实现。 如果FILL_ENTRY或所有收件人的属性需要更新（例如创建时或一段时间尚未更新这些属性）时，请设置此标志。 
    
3. 如果 **OpenTemplateID** 返回了外提供程序的 **IMAPIProp** 实现，则向客户端返回指向此实现的指针。 
    
4. 如果 **OpenTemplateID** 不返回实现（通常是因为外提供程序不在配置文件中）则向客户端返回指向提供程序 **的 IMAPIProp** 实现指针。 客户端应该能够使用任一接口处理对象的属性。 
    

