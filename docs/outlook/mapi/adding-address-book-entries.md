---
title: 添加通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 63444a65-d56a-4dbd-9aa6-e60f18ba8104
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: adbfbb73ac0f5f1e1cba547fa7a91393891fdb1c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774497"
---
# <a name="adding-address-book-entries"></a>添加通讯簿条目

  
  
**适用于**： Outlook 
  
将邮件用户或通讯组列表添加到容器、 客户端调用[IAddrBook::NewEntry](iaddrbook-newentry.md)或提供商呼叫与目标容器_lpEIDContainer_参数中的项标识符[IMAPISupport::NewEntry](imapisupport-newentry.md) 。 MAPI 轮流调用容器的[IABContainer::CreateEntry](iabcontainer-createentry.md)方法来创建使用一次性模板一次性表中的条目。 一个一次性模板允许客户端创建特定类型的一个新收件人。 大部分字段是可编辑。 _LpEntryID_参数指向该模板可能的您的提供商提供，或者如果您的提供商支持外的模板，可能从一个外的提供程序，模板。 可以从外部模板创建收件人的提供程序实现的**CreateEntry**通常更多的提供程序不能实现比复杂。 
  
 **若要实现 IABContainer::CreateEntry**
  
1. 确定_lpEntryID_参数指定的项标识符的类型。 
    
2. 如果条目标识符代表消息的用户、 通讯组列表或您的提供商所拥有的通讯簿容器的模板：
    
1. 创建并初始化适当的对象。 如果需要，您的提供商可以设置一些初始属性。 这些属性取决于要创建的收件人的类型。 
    
2. 返回一个指针_lppMAPIPropEntry_参数的内容中的对象的实现。 
    
3. 如果条目标识符表示外的提供程序的模板：
    
1. 调用[IMAPISupport::OpenEntry](imapisupport-openentry.md)打开外的对象。 
    
2. 调用对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法，传递 NULL 属性标记数组，若要检索其属性。 
    
3. 编辑从**GetProps**通过更改属性标记为 PR_NULL 将不应用于新的对象并不会传输的所有属性返回的属性值数组。 
    
4. 创建新的对象的项标识符。 
    
5. 创建相应的新的对象类型，或者是消息的用户或通讯组列表。
    
6. 初始化新对象，通过设置默认属性。
    
7. 检查外来对象支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。 
    
8. 如果外来对象支持**PR_TEMPLATEID**，呼叫[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)外的提供程序检索属性对象接口，并将_lppMAPIPropEntry_参数的内容设置为 foreign 属性对象实现。 
    
9. 如果外来对象不支持**PR_TEMPLATEID**，设置为新的对象的提供程序的实现_lppMAPIPropEntry_参数的内容。 
    
10. 调用指向_lppMAPIPropEntry_参数从外来对象设置的相应属性的对象的[IMAPIProp::SetProps](imapiprop-setprops.md)方法。 
    

