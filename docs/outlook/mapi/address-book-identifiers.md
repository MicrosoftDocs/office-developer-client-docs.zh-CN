---
title: 通讯簿标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 40f6c699-86aa-4324-a30d-12c8f1e2de9c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f9ba7a2a0752dea353e914aaa14a09046b993e5f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580521"
---
# <a name="address-book-identifiers"></a>通讯簿标识符

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
所有通讯簿提供程序都分配条目标识符使用**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 对其消息的用户和通讯组列表对象属性。 客户端应用程序使用这些条目标识符打开并访问分配到的对象。
  
通讯簿使使用其他三种类型的标识符来表示对象：
  
- 一次性条目标识符
    
- 一次性模板条目标识符
    
- 模板标识符
    
由于各种条目标识符和与他们已命名的相似性，则很容易成为混淆有关如何使用和创建每个类型。 
  
一次性条目标识符是用于打开和访问称为一次性的收件人或自定义的收件人的类型的项标识符。 One-offs 是不属于任何通讯簿提供程序配置文件中的收件人。 分配给 one-offs 的项标识符的一次性收件人使用专门保留的格式。 一次性条目标识符用于打开和访问对象，因为它们存储在 PR_ENTRYID 属性。
  
创建 one-offs 和一次性条目标识符：
  
- 当客户端应用程序的用户选择添加收件人不到一条消息的收件人列表表示通讯簿中的任何条目。
    
- 当客户端应用程序的用户选择添加收件人不到可修改通讯簿容器表示通讯簿中的任何条目。
    
- 当传输提供程序接收地址及其相关的通讯簿提供程序无法处理的消息。
    
- 当传输提供程序接收的消息与网关所属的地址。
    
在前两个的情况下，客户端调用**IAddrBook::CreateOneOff**要与新创建的一次性收件人关联的一次性条目标识符。 在第二两种情况下，传输提供程序调用**IMAPISupport::CreateOneOff**与外部地址相关联的一次性条目标识符。 有关详细信息，请参阅[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)和[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)。
  
一个一次性模板条目标识符是用于打开和访问用于创建 one-offs 模板的短期条目标识符。 通讯簿提供程序和 MAPI 提供模板输入创建特定类型的收件人所需的信息。 有关这些模板，包括其条目标识符信息发布在一次性表中。 一次性表显示 MAPI 呼叫**IABLogon::GetOneOffTable**方法或通讯簿容器**IMAPIProp::OpenProperty**方法以请求**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 时属性或提供程序时调用**IMAPISupport::GetOneOffTable**。 有关详细信息，请参阅[IABLogon::GetOneOffTable](iablogon-getoneofftable.md)、 [IMAPIProp::OpenProperty](imapiprop-openproperty.md)和[IMAPISupport::GetOneOffTable](imapisupport-getoneofftable.md)。
  
若要创建一个新一次性，在用户选择一个一次性表中列出的模板。 客户端将从所选的行，这是所选模板的一次性模板条目标识符，PR_ENTRYID 列传递到**IAddrBook::NewEntry** _lpEIDNewEntryTpl_参数中。 有关详细信息，请参阅[IAddrBook::NewEntry](iaddrbook-newentry.md)。 MAPI 使用一次性模板条目标识符显示模板并允许用户输入创建收件人所需的信息。 
  
模板标识符是一些通讯簿提供程序分配给其收件人除了 PR_ENTRYID 属性中保留的项标识符的项标识符。 提供程序设置收件人的**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性来存储其模板标识符。 某些通讯簿提供程序分配相同的收件人的模板标识符和条目标识符属性值。
  
模板标识符仅通讯簿提供程序和使用 MAPI 一个提供程序中绑定收件人数据、 称为宿主提供程序，到另一个提供程序中的收件人的代码，称为外的提供程序。 宿主提供程序提供的收件人，则为存储外的提供程序提供逻辑。 绑定过程启用更新的收件人，它将存储使用外的提供程序的代码数据的宿主提供程序。
  
已准备好修改其收件人宿主提供程序时，它将启动绑定过程**IMAPISupport::OpenTemplateID**方法调用中传递 PR_TEMPLATEID 属性。 通过将模板标识符传送到适当外提供程序通过对其**IABLogon::OpenTemplateID**方法的调用，MAPI 继续执行过程。 有关详细信息，请参阅[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)和[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)。 外的提供程序返回的收件人，宿主提供程序可以使用它自己的实现代替其**IMAPIProp**实现的指针。 
  

