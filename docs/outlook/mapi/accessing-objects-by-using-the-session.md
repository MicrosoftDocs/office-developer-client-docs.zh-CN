---
title: 使用会话访问对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ecada707-2960-41ec-be7e-619cad257c57
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a76397b74642aedf9ad5c9704735d869f61db7e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410537"
---
# <a name="accessing-objects-by-using-the-session"></a>使用会话访问对象

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过调用 [MAPILogonEx](mapilogonex.md) 收到的会话指针可用于访问各种对象。 下表列出了用于访问各种对象的方法： 
  
|**Object**|**Session 方法**|
|:-----|:-----|
|配置文件部分  <br/> |[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) <br/> |
|邮件存储  <br/> |[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) <br/> |
|通讯簿  <br/> |[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md) <br/> |
|邮件服务管理对象  <br/> |[IMAPISession::AdminServices](imapisession-adminservices.md) <br/> |
|文件夹、邮件、通讯簿容器、通讯组列表或邮件用户  <br/> |[IMAPISession::OpenEntry](imapisession-openentry.md) <br/> |
   
使用 **OpenEntry** 方法和有效的条目标识符，可以打开任何通讯簿或邮件存储提供程序对象。 除了 **IMAPISession** 方法之外，MAPI 中还有其他 **OpenEntry** 方法。 **OpenEntry** 在下列对象中实现： 
  
|**Object**|**方法**|
|:-----|:-----|
|通讯簿提供程序的登录对象  <br/> |[IABLogon::OpenEntry](iablogon-openentry.md) <br/> |
|通讯簿  <br/> |[IAddrBook::OpenEntry](iaddrbook-openentry.md) <br/> |
|通讯簿容器  <br/> |[IMAPIContainer::OpenEntry](imapicontainer-openentry.md) <br/> |
|会话  <br/> |[IMAPISession::OpenEntry](imapisession-openentry.md) <br/> |
|邮件存储  <br/> |[IMsgStore::OpenEntry](imsgstore-openentry.md) <br/> |
|邮件存储提供程序的登录对象  <br/> |[IMSLogon::OpenEntry](imslogon-openentry.md) <br/> |
|文件夹  <br/> |[IMAPIContainer::OpenEntry](imapicontainer-openentry.md) <br/> |
|Support 对象  <br/> |[IMAPISupport::OpenEntry](imapisupport-openentry.md) <br/> |
   
某些 **OpenEntry** 方法需要打开对象的条目标识符 **，IMAPISession：：OpenEntry**;其他方法允许指定 NULL。 NULL 条目标识符的解析方式因对象不同而不同。 例如，当您使用 NULL 条目标识符 **调用 IAddrBook：：OpenEntry** 时，MAPI 将打开通讯簿的根容器。 邮件存储的 **OpenEntry** 方法的行为类似;它将打开邮件存储的根文件夹。 **由文件夹和通讯簿容器实现的 IMAPIContainer：：OpenEntry** 可能会MAPI_E_INVALID_PARAMETER或根容器，具体取决于实现者。 
  
除了禁止输入标识符的 NULL 值之外，会话的 **OpenEntry** 方法与其他 **OpenEntry** 方法不同，因为它的作业不是打开对象。 相反，它会检查条目标识符，将调用转发到另一个由相应服务提供商实现的 **OpenEntry** 方法。 例如，如果使用邮件的条目标识符调用 **IMAPISession：：OpenEntry，MAPI** 将调用负责邮件的邮件存储的 **IMSLogon：：OpenEntry** 方法。 
  
除了使用会话打开对象之外，客户端还使用它来比较它们。 [IMAPISession：：CompareEntryIDs](imapisession-compareentryids.md)方法通过比较对象的条目标识符来比较对象。 如果 [条目标识符中包含的 MAPIUID](mapiuid.md) 结构属于同一服务提供商，MAPI 将调用转发给该提供程序。 **当两个条目标识符不匹配时，CompareEntryIDs** 将返回错误值。 虽然此方法可以比较属于任何类型的对象的条目标识符， **但 CompareEntryIDs** 最适用于邮件存储和通讯簿容器等更高级别的对象。 若要比较较低级别的对象，请直接比较对象的搜索键 (**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) ) 或记录 (**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) ) 。 
  
与 **OpenEntry** 一样 **，CompareEntryIDs** 由多个对象实现。 根据所打开或比较的对象的信息量，选择使用哪种 **OpenEntry** 和 **CompareEntryID** 方法。 在确定要调用的接口方法时，请使用以下指南： 
  
- 如果没有有关目标对象的信息，请调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 或 [IMAPISession：：CompareEntryIDs](imapisession-compareentryids.md)。 此方法允许访问任何对象，但这三个对象中最慢。
    
- 如果您知道目标对象是通讯簿条目，而不是文件夹等，请调用 [IAddrBook：：OpenEntry](iaddrbook-openentry.md) 或 [IAddrBook：：CompareEntryIDs](iaddrbook-compareentryids.md) 方法。 将 NULL 指定为目标对象时 **，IAddrBook：：OpenEntry** 将打开通讯簿的根容器。 此方法允许访问任何通讯簿对象，并且比使用 **IMAPISession** 速度更快，但比使用 **IMAPIContainer 慢**。
    
- 如果所使用的条目标识符是短期条目标识符，或者如果你知道目标对象属于特定的通讯簿容器或文件夹，请调用 [IMAPIContainer：：OpenEntry](imapicontainer-openentry.md) 方法。 此方法可产生最快性能，但仅允许访问特定容器或文件夹中的对象。 
    

