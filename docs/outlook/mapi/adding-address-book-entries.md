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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421338"
---
# <a name="adding-address-book-entries"></a>添加通讯簿条目

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要将消息传送用户或通讯组列表添加到容器，客户端调用 [IAddrBook：：NewEntry](iaddrbook-newentry.md) 或提供程序调用 [IMAPISupport：：NewEntry，](imapisupport-newentry.md) 其中  _lpEIDContainer_ 参数中目标容器的条目标识符。 MAPI 反过来调用容器的 [IABContainer：：CreateEntry](iabcontainer-createentry.md) 方法，以使用一次表中的一次模板创建条目。 一次模板允许客户端创建一个特定类型的新收件人。 大多数字段都是可编辑的。 _lpEntryID_ 参数指向的模板可能是提供程序提供的模板，或者，如果提供程序支持外模板，则它可能是来自外提供程序的模板。 对于可以从外模板创建收件人的提供程序 **，CreateEntry** 的实现始终比无法实现提供程序的实现更复杂。 
  
 **实现 IABContainer：：CreateEntry**
  
1. 确定  _lpEntryID_ 参数指定的条目标识符的类型。 
    
2. 如果条目标识符表示提供程序所拥有的邮件用户、通讯组列表或通讯簿容器的模板：
    
1. 创建并初始化相应的对象。 如果需要，提供程序可以设置一些初始属性。 这些属性取决于所创建的收件人的类型。 
    
2. 在  _lppMAPIPropEntry_ 参数的内容中返回一个指向对象实现指针。 
    
3. 如果条目标识符表示一个外提供程序的模板：
    
1. 调用 [IMAPISupport：：OpenEntry](imapisupport-openentry.md) 以打开外对象。 
    
2. 调用对象的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法，为属性标记数组传递 NULL 以检索其属性。 
    
3. 编辑从 **GetProps** 返回的属性值数组，将属性标记PR_NULL不应用于新对象且不应传输的所有属性的属性值数组。 
    
4. 创建新对象的条目标识符。 
    
5. 创建适当类型的新对象，可以是邮件用户或通讯组列表。
    
6. 通过设置默认属性初始化新对象。
    
7. 检查外对象是否支持[PidTagTemplateid PR_TEMPLATEID (PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 对象。  
    
8. 如果外对象支持 **PR_TEMPLATEID，** 请调用 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md) 从外提供程序检索属性对象接口，将  _lppMAPIPropEntry_ 参数的内容设置为 foreign 属性对象实现。 
    
9. 如果 foreign 对象不支持 **PR_TEMPLATEID，将**  _lppMAPIPropEntry_ 参数的内容设置为提供程序的新对象的实现。 
    
10. 调用 _lppMAPIPropEntry_ 参数指向的对象的 [IMAPIProp：：SetProps](imapiprop-setprops.md)方法，以设置来自外对象的适当属性。 
    

