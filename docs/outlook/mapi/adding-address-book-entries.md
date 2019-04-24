---
title: 添加通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 63444a65-d56a-4dbd-9aa6-e60f18ba8104
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8dc82a99ee088d42c076ca9a3a75eac6553f7d35
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331876"
---
# <a name="adding-address-book-entries"></a>添加通讯簿条目

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要向容器中添加邮件用户或通讯组列表, 客户端调用[IAddrBook:: NewEntry](iaddrbook-newentry.md)或 provider 使用_lpEIDContainer_参数中的目标容器的条目标识符调用[IMAPISupport:: NewEntry](imapisupport-newentry.md) 。 MAPI 反过来会调用容器的[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法, 以使用一次性的一次性模板创建条目。 一次性模板允许客户端创建特定类型的新收件人。 大部分字段都是可编辑的。 如果您的提供程序支持外部模板, 则由_lpEntryID_参数指向的模板可能是提供程序提供的模板, 也可能是来自外部提供程序的模板。 可从外部模板创建收件人的提供程序的**CreateEntry**的实现通常比无法实现的提供程序更复杂。 
  
 **实现 IABContainer:: CreateEntry**
  
1. 确定由_lpEntryID_参数指定的条目标识符的类型。 
    
2. 如果条目标识符代表邮件用户、通讯组列表或提供商拥有的通讯簿容器的模板:
    
1. 创建并初始化相应的对象。 提供程序可以根据需要设置一些初始属性。 这些属性取决于所创建的收件人的类型。 
    
2. 在_lppMAPIPropEntry_参数的内容中返回指向对象的实现的指针。 
    
3. 如果条目标识符表示外部提供程序的模板:
    
1. 调用[IMAPISupport:: OpenEntry](imapisupport-openentry.md)以打开外部对象。 
    
2. 调用该对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法, 并为该属性标记数组传递 NULL, 以检索其属性。 
    
3. 通过将不适用于新对象且不应转移的所有属性的属性标记更改为 PR_NULL, 可编辑从**GetProps**返回的属性值数组。 
    
4. 为新对象创建条目标识符。 
    
5. 创建一个适当类型的新对象, 即邮件用户或通讯组列表。
    
6. 通过设置默认属性来初始化新对象。
    
7. 检查外部对象是否支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。 
    
8. 如果外部对象支持**PR_TEMPLATEID**, 则调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)以检索来自外部提供程序的 property 对象接口, 并将_lppMAPIPropEntry_参数的内容设置为外部属性对象实现。 
    
9. 如果外部对象不支持**PR_TEMPLATEID**, 请将_lppMAPIPropEntry_参数的内容设置为提供程序的新对象实现。 
    
10. 调用_lppMAPIPropEntry_参数指向的对象的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法, 以设置外部对象的相应属性。 
    

