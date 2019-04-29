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
  
从对[MAPILogonEx](mapilogonex.md)的调用中接收到的会话指针可用于访问各种各样的对象。 下表列出了用于访问各种对象的方法: 
  
|**Object**|**Session 方法**|
|:-----|:-----|
|Profile 部分  <br/> |[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) <br/> |
|邮件存储  <br/> |[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) <br/> |
|通讯簿  <br/> |[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md) <br/> |
|邮件服务管理对象  <br/> |[IMAPISession::AdminServices](imapisession-adminservices.md) <br/> |
|文件夹、邮件、通讯簿容器、通讯组列表或邮件用户  <br/> |[IMAPISession::OpenEntry](imapisession-openentry.md) <br/> |
   
使用**OpenEntry**方法和有效的条目标识符, 可以打开任何通讯簿或邮件存储提供程序对象。 除了**IMAPISession**方法之外, MAPI 中还有其他**OpenEntry**方法。 **OpenEntry**在以下对象中实现: 
  
|**Object**|**方法**|
|:-----|:-----|
|通讯簿提供程序的登录对象  <br/> |[IABLogon::OpenEntry](iablogon-openentry.md) <br/> |
|通讯簿  <br/> |[IAddrBook::OpenEntry](iaddrbook-openentry.md) <br/> |
|通讯簿容器  <br/> |[IMAPIContainer::OpenEntry](imapicontainer-openentry.md) <br/> |
|Session  <br/> |[IMAPISession::OpenEntry](imapisession-openentry.md) <br/> |
|邮件存储  <br/> |[IMsgStore::OpenEntry](imsgstore-openentry.md) <br/> |
|邮件存储提供程序的登录对象  <br/> |[IMSLogon::OpenEntry](imslogon-openentry.md) <br/> |
|Folder  <br/> |[IMAPIContainer::OpenEntry](imapicontainer-openentry.md) <br/> |
|支持对象  <br/> |[IMAPISupport::OpenEntry](imapisupport-openentry.md) <br/> |
   
某些**OpenEntry**方法需要要打开的对象的条目标识符, **IMAPISession:: OpenEntry**;其他方法允许指定 NULL 值。 根据对象的不同, 将以不同的方式解释 NULL 条目标识符。 例如, 当您使用 NULL 条目标识符调用**IAddrBook:: OpenEntry**时, MAPI 将打开通讯簿的根容器。 邮件存储区的**OpenEntry**方法的行为与此类似。它打开邮件存储区的根文件夹。 **IMAPIContainer:: OpenEntry**, 由文件夹和通讯簿容器同时实现, 可能会返回 MAPI_E_INVALID_PARAMETER 或根容器, 具体取决于实施者。 
  
除了对条目标识符禁用 NULL 值之外, 该会话的**OpenEntry**方法与其他**OpenEntry**方法不同, 因为它的作业不是打开对象。 相反, 它会检查条目标识符, 并将该呼叫转发给由相应的服务提供程序实现的另一个**OpenEntry**方法。 例如, 如果使用邮件的条目标识符调用**IMAPISession:: OpenEntry** , 则 MAPI 将调用负责邮件的邮件存储区的**IMSLogon:: OpenEntry**方法。 
  
除了使用会话打开对象之外, 客户端也使用该会话来比较这些对象。 [IMAPISession:: CompareEntryIDs](imapisession-compareentryids.md)方法通过比较对象的条目标识符对对象进行比较。 如果条目标识符中包含的[MAPIUID](mapiuid.md)结构属于同一服务提供程序, MAPI 会将呼叫转发给该提供商。 当两个条目标识符不匹配时, **CompareEntryIDs**将返回一个错误值。 虽然此方法可以比较属于任何类型的对象的条目标识符, 但**CompareEntryIDs**最适用于更高级别的对象, 如邮件存储和通讯簿容器。 若要比较较低级别的对象, 请直接比较对象的搜索关键字 (**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))) 或 record 关键字 (**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)))。 
  
与**OpenEntry**一样, **CompareEntryIDs**由多个对象实现。 根据要打开或比较的对象的信息量, 选择要使用的**OpenEntry**和**CompareEntryID**方法。 在决定要调用哪种接口方法时, 请使用以下准则: 
  
- 如果您没有有关目标对象的信息, 请调用[IMAPISession:: OpenEntry](imapisession-openentry.md)或[IMAPISession:: CompareEntryIDs](imapisession-compareentryids.md)。 此方法支持对任何对象的访问, 但这是最慢的三种方法。
    
- 如果您知道目标对象是通讯簿条目而不是文件夹, 例如, 文件夹, 请调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md)或[IAddrBook:: CompareEntryIDs](iaddrbook-compareentryids.md)方法。 **IAddrBook:: OpenEntry**当将 NULL 指定为目标对象时, 将打开通讯簿的根容器。 此方法支持对任何通讯簿对象的访问, 比使用**IMAPISession**速度更快, 但速度慢于使用**IMAPIContainer**。
    
- 如果正在使用的条目标识符是短期条目标识符, 或者如果您知道目标对象属于特定的通讯簿容器或文件夹, 请调用[IMAPIContainer:: OpenEntry](imapicontainer-openentry.md)方法。 此方法可获得速度最快的性能, 但只能访问特定容器或文件夹中的对象。 
    

