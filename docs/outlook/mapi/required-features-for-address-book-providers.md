---
title: 通讯簿提供程序的必需功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e2ccddd7-65e8-41f6-8e21-a4ae98190a96
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ac76d1caf5db0b041a17d40d08671665b5427051
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778619"
---
# <a name="required-features-for-address-book-providers"></a>通讯簿提供程序的必需功能

  
  
**适用于**： Outlook 
  
通讯簿提供程序可以使用的临时或永久、 本地或远程、 一个或多个邮件系统，理解和磁盘文件或数据库表的格式化的收件人信息。 有多种通讯簿提供程序可以实现，从而添加值和改进与客户端和其他提供程序的互操作性的功能。 但是，所需的一些功能。
  
下表介绍所需的所有通讯簿提供程序的功能和需要实现它们所需的步骤。
  
|**功能**|**如何实现**|
|:-----|:-----|
|会话登录  <br/> | 实现入口点函数。 有关详细信息，请参阅[实现地址簿提供程序入口点函数](implementing-an-address-book-provider-entry-point-function.md)。  <br/>  实现[IABProvider::Logon](iabprovider-logon.md)方法。 有关详细信息，请参阅[实现通讯簿提供程序登录和注销](implementing-address-book-provider-logon-and-logoff.md)。  <br/> |
|会话注销  <br/> |实现[IABProvider::Shutdown](iabprovider-shutdown.md)方法。 有关详细信息，请参阅[实现通讯簿提供程序登录和注销](implementing-address-book-provider-logon-and-logoff.md)。  <br/> |
|创建条目标识符  <br/> |提供支持**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 有关详细信息，请参阅[MAPI 条目标识符](mapi-entry-identifiers.md)和[通讯簿标识符](address-book-identifiers.md)。  <br/> |
|参与状态表  <br/> | 实现相应方法的[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。 有关详细信息，请参阅[状态对象实现](status-object-implementation.md)。  <br/>  支持所需的状态表属性。 有关详细信息，请参阅[状态表](status-tables.md)。  <br/>  调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)。  <br/> |
|提供有限的状态对象支持  <br/> | 实现[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。  <br/>  从其他**IMAPIStatus**方法返回 MAPI_E_NO_SUPPORT。  <br/> |
|支持互动模板和编程配置  <br/> | 实现消息服务入口点函数。  <br/>  实现显示表。 有关详细信息，请参阅[显示表](display-tables.md)和[显示表实现](display-table-implementation.md)。  <br/>  实现属性表或调用[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)方法。 有关详细信息，请参阅[属性表实现](property-sheet-implementation.md)。  <br/> |
   
此外，如果您的提供商支持收件人的创建，您必须提供创建模板的列表。 通过实现[IABLogon::GetOneOffTable](iablogon-getoneofftable.md)方法，以包括所有支持您的提供程序和每个容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法打开**PR_CREATE_TEMPLATES** ([模板提供此列表PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性，包括所有支持的容器的模板。 有关详细信息，请参阅[实现一次性表](implementing-one-off-tables.md)。
  

