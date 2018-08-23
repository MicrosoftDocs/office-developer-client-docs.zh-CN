---
title: 通讯簿容器的必需功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3e221944-5dc9-4cce-8b47-73af84427aea
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 050a26f4b4e6c353881189f8c7b71c2e4c378d03
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577210"
---
# <a name="required-features-for-address-book-containers"></a>通讯簿容器的必需功能

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
大多数通讯簿提供程序支持至少一个容器，可修改其中一些。 通讯簿容器可以提供内容和层次结构表、 搜索功能和名称解析。 可修改容器允许删除如消息用户、 通讯组列表，或其他容器和项从其他容器中条目或一次性模板添加条目。
  
下表描述功能所需的通讯簿提供程序的容器，可修改或只读的并实现它们。
  
|**功能**|**如何实现**|
|:-----|:-----|
|访问邮件用户  <br/> |实现[IABLogon::OpenEntry](iablogon-openentry.md)方法。 有关详细信息，请参阅[打开通讯簿条目](opening-address-book-entries.md)。  <br/> |
|比较消息的用户  <br/> |实现[IABLogon::CompareEntryIDs](iablogon-compareentryids.md)方法。 有关详细信息，请参阅[比较通讯簿条目](comparing-address-book-entries.md)。  <br/> |
|创建邮件用户  <br/> |1.提供一次性表中创建模板的列表支持**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 有关详细信息，请参阅[实现容器一次性表](implementing-a-container-one-off-table.md)。  <br/> 2.实现[IABContainer::CreateEntry](iabcontainer-createentry.md)方法。 有关详细信息，请参阅[添加通讯簿条目](adding-address-book-entries.md)。  <br/> |
|复制邮件的用户  <br/> |实现[IABContainer::CopyEntries](iabcontainer-copyentries.md)方法。 有关详细信息，请参阅[复制通讯簿条目](copying-address-book-entries.md)。  <br/> |
|删除消息的用户  <br/> |实现[IABContainer::DeleteEntries](iabcontainer-deleteentries.md)方法。 有关详细信息，请参阅[删除通讯簿条目](removing-address-book-entries.md)。  <br/> |
|提供有关邮件用户的摘要信息  <br/> |支持的容器属性**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))。 有关详细信息，请参阅[内容表](contents-tables.md)。  <br/> |
|提供了有关消息用户的详细的信息  <br/> |消息用户和通讯组列表上支持**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 的属性。 有关详细信息，请参阅[显示收件人信息](displaying-recipient-information.md)和[显示表格](display-tables.md)。  <br/> |
|提供了有关容器的详细的信息  <br/> |支持的容器上**PR_DETAILS_TABLE**属性。 有关详细信息，请参阅[显示收件人信息](displaying-recipient-information.md)和[显示表格](display-tables.md)。  <br/> |
|提供容器的分层列表  <br/> |支持的容器属性**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))。 有关详细信息，请参阅[层次结构表](hierarchy-tables.md)。  <br/> |
|支持消息的用户属性  <br/> |实现[IMailUser: IMAPIProp](imailuserimapiprop.md)接口。  <br/> |
|解析不确定的名称  <br/> | 支持**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制。  <br/>  （可选） 实现[IABContainer::ResolveNames](iabcontainer-resolvenames.md)方法。 有关详细信息，请参阅[实现名称解析](implementing-name-resolution.md)。  <br/> |
   

