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
ms.openlocfilehash: 56ca15440c8d323dbab1b6a92a01941106b86934
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421394"
---
# <a name="required-features-for-address-book-providers"></a>通讯簿提供程序的必需功能

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿提供程序可处理临时或永久、本地或远程的收件人信息、由一个或多个邮件系统理解的收件人信息, 以及针对磁盘文件或数据库表的格式。 通讯簿提供程序可以实现多种功能, 从而增加价值并提高与客户端和其他提供程序的互操作性。 但是, 有些功能是必需的。
  
下表介绍了所有通讯簿提供程序所需的功能以及实现这些功能需要执行的步骤。
  
|**功能**|**如何实现**|
|:-----|:-----|
|会话登录  <br/> | 实现入口点函数。 有关详细信息, 请参阅[实现通讯簿提供程序入口点函数](implementing-an-address-book-provider-entry-point-function.md)。  <br/>  实现[IABProvider:: Logon](iabprovider-logon.md)方法。 有关详细信息, 请参阅[实现通讯簿提供程序登录和注销](implementing-address-book-provider-logon-and-logoff.md)。  <br/> |
|会话注销  <br/> |实现[IABProvider:: Shutdown](iabprovider-shutdown.md)方法。 有关详细信息, 请参阅[实现通讯簿提供程序登录和注销](implementing-address-book-provider-logon-and-logoff.md)。  <br/> |
|创建条目标识符  <br/> |提供对**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的支持。 有关详细信息, 请参阅[MAPI 条目标识符](mapi-entry-identifiers.md)和[通讯簿标识符](address-book-identifiers.md)。  <br/> |
|对状态表的参与  <br/> | 实现[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口的相应方法。 有关详细信息, 请参阅[Status Object 实现](status-object-implementation.md)。  <br/>  支持所需的状态表属性。 有关详细信息, 请参阅[状态表](status-tables.md)。  <br/>  调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)。  <br/> |
|提供有限的状态对象支持  <br/> | 实现[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法。  <br/>  从其他**IMAPIStatus**方法返回 MAPI_E_NO_SUPPORT。  <br/> |
|支持交互式和编程配置  <br/> | 实现邮件服务入口点函数。  <br/>  实现显示表。 有关详细信息, 请参阅[显示表](display-tables.md)和[显示表实现](display-table-implementation.md)。  <br/>  实现属性表或调用[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法。 有关详细信息, 请参阅[Property Sheet 实现](property-sheet-implementation.md)。  <br/> |
   
此外, 如果您的提供商支持创建收件人, 则必须提供创建模板的列表。 通过实现[IABLogon:: GetOneOffTable](iablogon-getoneofftable.md)方法来提供此列表, 以包括您的提供程序支持的所有模板和每个容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法以打开**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性, 并包含该容器支持的所有模板。 有关详细信息, 请参阅[实现一次性表](implementing-one-off-tables.md)。
  

