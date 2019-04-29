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
ms.openlocfilehash: abdbd9030e0ea053d39b49ecc76a78821be9df82
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439679"
---
# <a name="required-features-for-address-book-containers"></a>通讯簿容器的必需功能

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
大多数通讯簿提供程序至少支持一个容器, 其中一些容器是可修改的。 通讯簿容器可以提供内容和层次结构表、搜索功能和名称解析。 可修改的容器允许删除邮件用户、通讯组列表或其他容器等条目, 以及在其他容器或一次性模板中添加条目的条目。
  
下表描述了通讯簿提供程序所需的功能, 这些提供程序具有容器、可修改的或只读的, 以及如何实施这些功能。
  
|**功能**|**如何实现**|
|:-----|:-----|
|访问邮件用户  <br/> |实现[IABLogon:: OpenEntry](iablogon-openentry.md)方法。 有关详细信息, 请参阅[打开通讯簿条目](opening-address-book-entries.md)。  <br/> |
|比较邮件用户  <br/> |实现[IABLogon:: CompareEntryIDs](iablogon-compareentryids.md)方法。 有关详细信息, 请参阅[比较通讯簿条目](comparing-address-book-entries.md)。  <br/> |
|创建邮件用户  <br/> |1. 通过支持**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性, 在一次性表格中提供创建模板的列表。 有关详细信息, 请参阅[实现容器一次性表](implementing-a-container-one-off-table.md)。  <br/> 2. 实现[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法。 有关详细信息, 请参阅[添加通讯簿条目](adding-address-book-entries.md)。  <br/> |
|复制邮件用户  <br/> |实现[IABContainer:: CopyEntries](iabcontainer-copyentries.md)方法。 有关详细信息, 请参阅[复制通讯簿条目](copying-address-book-entries.md)。  <br/> |
|删除邮件用户  <br/> |实现[IABContainer::D eleteentries](iabcontainer-deleteentries.md)方法。 有关详细信息, 请参阅[删除通讯簿条目](removing-address-book-entries.md)。  <br/> |
|提供有关邮件用户的摘要信息  <br/> |支持 container 属性**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))。 有关详细信息，请参阅[内容表](contents-tables.md)。  <br/> |
|提供有关邮件用户的详细信息  <br/> |支持邮件用户和通讯组列表上的**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 有关详细信息, 请参阅[显示收件人信息](displaying-recipient-information.md)和[显示表](display-tables.md)。  <br/> |
|提供有关容器的详细信息  <br/> |支持容器上的**PR_DETAILS_TABLE**属性。 有关详细信息, 请参阅[显示收件人信息](displaying-recipient-information.md)和[显示表](display-tables.md)。  <br/> |
|提供容器的分层列表  <br/> |支持 container 属性**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))。 有关详细信息, 请参阅[层次结构表](hierarchy-tables.md)。  <br/> |
|支持邮件用户属性  <br/> |实现[IMailUser: IMAPIProp](imailuserimapiprop.md)接口。  <br/> |
|解析模糊名称  <br/> | 支持**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制。  <br/>  (可选) 实现[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)方法。 有关详细信息, 请参阅[实现名称解析](implementing-name-resolution.md)。  <br/> |
   

