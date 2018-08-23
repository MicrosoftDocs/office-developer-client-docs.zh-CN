---
title: 创建收件人
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 586c901f-d9f9-44f2-a328-051775a81265
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4d4777077dae5effed9f233dd020628ee0dcfed5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578043"
---
# <a name="creating-a-recipient"></a>创建收件人

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
客户端创建收件人在其所撰写邮件时，以及何时向可修改通讯簿容器中添加条目。 MAPI 提供了用于创建收件人的三种方法：
  
- [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)
    
- [IAddrBook::NewEntry](iaddrbook-newentry.md)
    
- [IABContainer::CreateEntry](iabcontainer-createentry.md)
    
创建收件人用于邮件的地址时调用**IAddrBook::CreateOneOff** 。 **CreateOneOff**创建要与特定地址类型的地址关联的特殊格式一次性条目标识符。 有关 one-offs 和一次性条目标识符的详细信息，请参阅[一次性地址](one-off-addresses.md)和[一次性条目标识符](one-off-entry-identifiers.md)。
  
呼叫**IAddrBook::NewEntry**创建收件人是时使用以下任意电子邮件地址，或将添加到容器。 **NewEntry**具有三个对包含项标识符的参数。 这些参数如下所述： 
  
|**参数对**|**说明**|
|:-----|:-----|
| _cbEidContainer_和_lpEidContainer_ <br/> |应放置新条目的容器的项标识符。  <br/> |
| _cbEidNewEntryTpl_和_lpEidNewEntryTpl_ <br/> |要用于创建新项的模板的项标识符。  <br/> |
| _lpcbEidNewEntry_和_lppEidNewEntry_ <br/> |新条目的项标识符。  <br/> |
   
若要创建的传出邮件的收件人，设置为零，并为 NULL _lpEidContainer_ _cbEidContainer_ 。 **NewEntry**创建收件人符合一次性格式，通过调用**IAddrBook::CreateOneOff**生成的收件人的相同类型的项标识符。 
  
若要创建要插入到某个特定的容器的收件人，设置到容器的项标识符和_cbEidContainer_中容器的项标识符的字节数为_lpEidContainer_ 。 
  
若要使用模板创建收件人，设置为要使用的模板和_cbEidNewEntryTpl_为中此项标识符的字节数的项标识符的_lpEidNewEntryTpl_ 。 最可修改通讯簿容器支持一个或多个模板创建的特定类型的条目。 一次性模板通常是，但不是总是对话框。 输入到模板的信息将生成的收件人地址的格式正确的类型。 
  
从以下任意获取模板条目标识符：
  
- 在容器的一次性表中，通过调用容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法并指定**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 为访问**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列属性标记和 IID_IMAPITable 接口标识。 
    
- 通讯簿提供程序的**PR_DEF_CREATE_MAILUSER** ([PidTagDefCreateMailuser](pidtagdefcreatemailuser-canonical-property.md)) 和**PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) 属性，其保留的项标识符的提供程序的邮件用户对象和通讯组列表模板。 
    
> [!NOTE]
> 不要混淆与另一种称为模板标识符的项标识符的新条目模板的项标识符。 模板标识符仅使用提供程序以维护从其他提供程序; 复制的条目从不使用客户端并不用于创建新条目。 
  
若要允许用户以确定要创建的项的类型，请传递零_cbEidNewEntryTpl_和_lpEidNewEntryTpl_NULL。 **NewEntry**发生这种情况，当显示 MAPI 的一次性表中生成一个常见对话框 — 所有支持的配置文件中每个通讯簿提供程序的模板的分层列表。 
  
当确定地址类型，也**NewEntry** _lpEidNewEntryTpl_参数或一次性表格显示中的用户所选内容的设置，通过显示相应的模板使用其显示表。 所有新条目模板支持**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 的属性。 
  
若要有**NewEntry**返回创建的项的项标识符，传递的_lpcbEidNewEntry_和_lppEidNewEntry_参数的有效地址。 MAPI 将新的项标识符放所指的_lppEidNewEntry_和在由_lpcbEidNewEntry_指向地址的新项标识符的字节数的地址。
  
调用[IABContainer::CreateEntry](iabcontainer-createentry.md)创建收件人并将其保存到特定地址簿容器。 您可以使用此方法仅可修改容器 — 容器具有 AB_MODIFIABLE 标记其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中的设置。 与不可更改的容器的通讯簿提供程序不支持此方法。 指定用于创建_lpEntryID_参数中所需类型的项的模板的项标识符。 
  
_UlCreateFlags_参数中指定的检查所需的重复项和新条目应该替换现有的类型。 **CreateEntry**未能由于重复的条目，检查施加的提供程序创建新的对象，如果不希望看到错误或警告返回。 这些情况下，提供程序返回成功代码。 
  
如果直接使用容器，并且您知道完全容器可以创建的地址的类型，您可以调用**IABContainer::CreateEntry**并传递相应的模板的项标识符。 通讯簿提供程序设置一些初始默认属性;您可以调用**SetProps**设置其他人。 从不涉及用户。 
  

