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
  
所有通讯簿提供程序都使用 PR_ENTRYID ( [PidTagEntryId](pidtagentryid-canonical-property.md)) 属性为其邮件用户和通讯组列表对象分配条目标识符。 客户端应用程序使用这些条目标识符来打开和访问它们分配到的对象。
  
通讯簿使用三种其他类型的标识符来表示对象：
  
- 一次性条目标识符
    
- 一次使用模板条目标识符
    
- 模板标识符
    
由于条目标识符有多种且名称相似，因此很容易混淆如何使用和创建每种类型。 
  
一次输入标识符是一个条目标识符，用于打开和访问称为一次发送收件人或自定义收件人的收件人类型。 一对多是不属于配置文件中任何通讯簿提供程序的收件人。 分配给一次收件人的条目标识符使用专门为一次收件人保留的格式。 因为一次输入标识符用于打开和访问对象，所以它们存储在 PR_ENTRYID 属性中。
  
创建一对一条目标识符和一对一条目标识符：
  
- 当客户端应用程序的用户选择将未表示通讯簿中任何条目的收件人添加到邮件的收件人列表中时。
    
- 当客户端应用程序的用户选择将未表示通讯簿中任何条目的收件人添加到可修改的通讯簿容器时。
    
- 当传输提供程序收到地址无法由相关通讯簿提供程序处理的邮件时。
    
- 当传输提供程序收到包含属于网关的地址的邮件时。
    
在前两种情况下，客户端调用 **IAddrBook：：CreateOneOff** 将一次输入标识符与新创建的一次收件人关联。 在后两种情况下，传输提供程序调用 **IMAPISupport：：CreateOneOff** 以将一次输入标识符与外地址关联。 有关详细信息，请参阅 [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md) 和 [IMAPISupport：：CreateOneOff](imapisupport-createoneoff.md)。
  
一次模板条目标识符是一个短期条目标识符，用于打开和访问用于创建一对一的模板。 用于输入创建特定类型收件人所需信息的通讯簿提供程序和 MAPI 提供模板。 有关这些模板的信息（包括其条目标识符）在一次表中发布。 当 MAPI 调用 **IABLogon：：GetOneOffTable** 方法或通讯簿容器 **的 IMAPIProp：：OpenProperty** 方法以请求 **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性或提供程序调用 **IMAPISupport：：GetOneOffTable** 时，将显示一键式表。 有关详细信息，请参阅 [IABLogon：：GetOneOffTable](iablogon-getoneofftable.md) [、IMAPIProp：：OpenProperty](imapiprop-openproperty.md)和 [IMAPISupport：：GetOneOffTable](imapisupport-getoneofftable.md)。
  
若要创建新的一次一次，用户可选择一次表中列出的模板之一。 客户端将 PR_ENTRYID 列从所选行（所选模板的一键式模板条目标识符）传递给 _lpEIDNewEntryTpl_ 参数中的 **IAddrBook：：NewEntry。** 有关详细信息，请参阅 [IAddrBook：：NewEntry](iaddrbook-newentry.md)。 MAPI 使用一次模板条目标识符来显示模板，并允许用户输入创建收件人所需的信息。 
  
模板标识符是一个条目标识符，除了保留于 PR_ENTRYID 属性中的条目标识符之外，某些通讯簿提供程序还将其分配给其收件人。 提供程序使用[PidTagTemplateid PR_TEMPLATEID (PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 设置收件人的模板标识符。  某些通讯簿提供程序为收件人的模板标识符和条目标识符属性分配相同的值。
  
模板标识符仅由通讯簿提供程序和 MAPI 使用，用于将一个提供程序（称为宿主提供程序）中的收件人数据绑定到另一个提供程序（称为"外提供程序"）中收件人的代码。 宿主提供程序为收件人提供存储;外提供程序提供逻辑。 通过绑定过程，宿主提供程序能够使用外提供程序的代码更新其存储的收件人的数据。
  
当主机提供程序准备修改其收件人时，它会在调用 **IMAPISupport：：OpenTemplateID** 方法时传递 PR_TEMPLATEID 属性以启动绑定过程。 MAPI 通过调用其 **IABLogon：：OpenTemplateID** 方法，将模板标识符传输到相应的外提供程序，以继续执行此过程。 有关详细信息，请参阅 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md) 和 [IABLogon：：OpenTemplateID](iablogon-opentemplateid.md)。 该外提供程序返回一个指针，指向收件人的 **IMAPIProp** 实现，宿主提供程序可以使用该指针来表示其自己的实现。 
  

