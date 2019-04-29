---
title: 通讯簿标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 40f6c699-86aa-4324-a30d-12c8f1e2de9c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 822d83c4b77d06c2e000b391c7e229985470ccd3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421569"
---
# <a name="address-book-identifiers"></a>通讯簿标识符

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
所有通讯簿提供程序使用**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性为其邮件用户和通讯组列表对象分配条目标识符。 客户端应用程序使用这些条目标识符打开和访问分配给它们的对象。
  
通讯簿使用了三种其他类型的标识符来表示对象:
  
- 一次性条目标识符
    
- 一次性模板条目标识符
    
- 模板标识符
    
由于条目标识符的种类不同以及它们的命名相似之处, 因此很容易对每种类型的使用和创建方式感到困惑。 
  
一次性条目标识符是一个条目标识符, 用于打开和访问称为 "一次性" 或 "自定义收件人" 的收件人类型。 一项操作是不属于配置文件中的任何通讯簿提供程序的收件人。 分配给一次性的条目标识符使用专为一次性收件人保留的格式。 由于一次性条目标识符用于打开和访问对象, 因此它们存储在 PR_ENTRYID 属性中。
  
创建一次性条目标识符和一次性条目标识符:
  
- 当客户端应用程序的用户选择将不表示通讯簿中任何条目的收件人添加到邮件的收件人列表中时。
    
- 当客户端应用程序的用户选择将不表示通讯簿中任何条目的收件人添加到可修改的通讯簿容器中时。
    
- 当传输提供程序接收到地址不能由其相关通讯簿提供程序处理的邮件时。
    
- 传输提供程序接收到地址属于网关的邮件时。
    
在前两种情况下, 客户端调用**IAddrBook:: CreateOneOff**将一次性条目标识符与新创建的一次性收件人相关联。 在这两种情况下, 传输提供程序调用**IMAPISupport:: CreateOneOff**将一次性条目标识符与外部地址关联。 有关详细信息, 请参阅[IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md)和[IMAPISupport:: CreateOneOff](imapisupport-createoneoff.md)。
  
一次性模板条目标识符是一个短期条目标识符, 用于打开和访问用于创建一次性的模板。 通讯簿提供程序和 MAPI 提供模板, 用于输入创建特定类型的收件人所需的信息。 有关这些模板的信息 (包括其条目标识符) 在一次性表中发布。 当 MAPI 调用**IABLogon:: GetOneOffTable**方法或通讯簿容器的**IMAPIProp:: OpenProperty**方法以请求**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 时, 将显示一次性表属性或提供程序调用**IMAPISupport:: GetOneOffTable**时。 有关详细信息, 请参阅[IABLogon:: GetOneOffTable](iablogon-getoneofftable.md)、 [IMAPIProp:: OpenProperty](imapiprop-openproperty.md)和[IMAPISupport:: GetOneOffTable](imapisupport-getoneofftable.md)。
  
若要创建新的一次性注销, 用户可以选择一次性表中列出的模板之一。 客户端将 PR_ENTRYID 列从选定的行 (所选模板的一次性模板条目标识符) 传递到_lpEIDNewEntryTpl_参数中的**IAddrBook:: NewEntry** 。 有关详细信息, 请参阅[IAddrBook:: NewEntry](iaddrbook-newentry.md)。 MAPI 使用一次性模板条目标识符来显示模板, 并允许用户输入创建收件人所需的信息。 
  
模板标识符是一个条目标识符, 除了 PR_ENTRYID 属性中保留的条目标识符外, 某些通讯簿提供程序会将其分配给收件人。 提供程序设置收件人的**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性以存储其模板标识符。 某些通讯簿提供程序为收件人的模板标识符和条目标识符属性分配相同的值。
  
模板标识符仅由通讯簿提供程序和 MAPI 用于将一个提供程序 (称为主机提供程序) 中的收件人数据绑定到另一个提供程序中的收件人代码 (称为外部提供程序)。 主机提供程序为收件人提供存储空间;外部提供程序提供逻辑。 绑定过程使主机提供程序能够使用外部提供程序的代码更新其存储的收件人的数据。
  
当主机提供程序准备好修改其收件人时, 它会在对**IMAPISupport:: OpenTemplateID**方法的调用中传递 PR_TEMPLATEID 属性以启动绑定过程。 MAPI 通过对其**IABLogon:: OpenTemplateID**方法的调用, 将模板标识符传输给适当的外部提供程序, 从而继续执行此过程。 有关详细信息, 请参阅[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)和[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)。 外部提供程序返回指向其**IMAPIProp**实现的指针, 宿主提供程序可以使用它来取代自己的实现。 
  

