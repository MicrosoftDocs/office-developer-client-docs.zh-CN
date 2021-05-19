---
title: 通讯簿提供程序所需的功能
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
# <a name="required-features-for-address-book-providers"></a>通讯簿提供程序所需的功能

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿提供程序可以使用临时或永久、本地或远程、一个或多个邮件系统可以理解的收件人信息，并针对磁盘文件或数据库表设置格式。 通讯簿提供程序可以实施多种功能，从而增加价值并改进与客户端和其他提供程序的互操作性。 但是，需要一些功能。
  
下表介绍了所有通讯簿提供程序所需的功能以及实现这些功能所需执行的步骤。
  
|**功能**|**如何实现**|
|:-----|:-----|
|会话登录  <br/> | 实现入口点函数。 有关详细信息，请参阅 [实现通讯簿提供程序入口点函数](implementing-an-address-book-provider-entry-point-function.md)。  <br/>  实现 [IABProvider：：Logon](iabprovider-logon.md) 方法。 有关详细信息，请参阅 [实现通讯簿提供程序登录和注销](implementing-address-book-provider-logon-and-logoff.md)。  <br/> |
|会话注销  <br/> |实现 [IABProvider：：Shutdown](iabprovider-shutdown.md) 方法。 有关详细信息，请参阅 [实现通讯簿提供程序登录和注销](implementing-address-book-provider-logon-and-logoff.md)。  <br/> |
|创建条目标识符  <br/> |为[PidTagEntryId PR_ENTRYID (PidTagEntryId](pidtagentryid-canonical-property.md)) 支持。  有关详细信息，请参阅 [MAPI 条目标识符](mapi-entry-identifiers.md) 和 [通讯簿标识符](address-book-identifiers.md)。  <br/> |
|参与状态表  <br/> | 实现 [IMAPIStatus ： IMAPIProp 接口的适当](imapistatusimapiprop.md) 方法。 有关详细信息，请参阅 [状态对象实现](status-object-implementation.md)。  <br/>  支持所需的状态表属性。 有关详细信息，请参阅状态 [表](status-tables.md)。  <br/>  调用 [IMAPISupport：：ModifyStatusRow](imapisupport-modifystatusrow.md)。  <br/> |
|提供有限的状态对象支持  <br/> | 实现 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法。  <br/>  返回MAPI_E_NO_SUPPORT **IMAPIStatus** 方法中的值。  <br/> |
|支持交互式和编程配置  <br/> | 实现邮件服务入口点函数。  <br/>  实现显示表。 有关详细信息，请参阅显示 [表](display-tables.md) 和 [显示表实现](display-table-implementation.md)。  <br/>  实现属性表或调用 [IMAPISupport：:D oConfigPropsheet](imapisupport-doconfigpropsheet.md) 方法。 有关详细信息，请参阅属性 [表实现](property-sheet-implementation.md)。  <br/> |
   
此外，如果您的提供程序支持收件人创建，则必须提供创建模板的列表。 通过实现 [IABLogon：：GetOneOffTable](iablogon-getoneofftable.md) 方法提供此列表，以包含提供程序支持的所有模板以及每个容器的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法，以打开 **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性并包括容器支持的所有模板。 有关详细信息，请参阅实现One-Off[表。](implementing-one-off-tables.md)
  

