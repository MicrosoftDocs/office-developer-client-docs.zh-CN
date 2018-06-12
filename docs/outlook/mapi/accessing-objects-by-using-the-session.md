---
title: 使用会话中访问对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ecada707-2960-41ec-be7e-619cad257c57
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ee20e73e5bc7bb6854b956da541d3a318a267d0f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774509"
---
# <a name="accessing-objects-by-using-the-session"></a>使用会话中访问对象

  
  
**适用于**： Outlook 
  
您收到来自呼叫到[MAPILogonEx](mapilogonex.md)会话指针可用于访问各种对象。 下表列出了用于访问各种对象的方法： 
  
|**对象**|**会话方法**|
|:-----|:-----|
|配置文件节  <br/> |[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) <br/> |
|消息存储库  <br/> |[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) <br/> |
|通讯簿  <br/> |[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md) <br/> |
|消息服务管理对象  <br/> |[IMAPISession::AdminServices](imapisession-adminservices.md) <br/> |
|文件夹、 邮件、 通讯簿容器、 通讯组列表或消息的用户  <br/> |[IMAPISession::OpenEntry](imapisession-openentry.md) <br/> |
   
使用**OpenEntry**方法和有效项标识符，您可以打开任何通讯簿或消息存储提供程序对象。 还有其他**OpenEntry**方法中 MAPI，除了**IMAPISession**方法。 在下列对象中实现**OpenEntry** : 
  
|**对象**|**方法**|
|:-----|:-----|
|通讯簿提供程序的登录对象  <br/> |[IABLogon::OpenEntry](iablogon-openentry.md) <br/> |
|通讯簿  <br/> |[IAddrBook::OpenEntry](iaddrbook-openentry.md) <br/> |
|通讯簿容器  <br/> |[IMAPIContainer::OpenEntry](imapicontainer-openentry.md) <br/> |
|会话  <br/> |[IMAPISession::OpenEntry](imapisession-openentry.md) <br/> |
|消息存储库  <br/> |[IMsgStore::OpenEntry](imsgstore-openentry.md) <br/> |
|消息存储提供程序的登录对象  <br/> |[IMSLogon::OpenEntry](imslogon-openentry.md) <br/> |
|Folder  <br/> |[IMAPIContainer::OpenEntry](imapicontainer-openentry.md) <br/> |
|支持对象  <br/> |[IMAPISupport::OpenEntry](imapisupport-openentry.md) <br/> |
   
某些**OpenEntry**方法要求要在打开的对象的项标识符，一样**IMAPISession::OpenEntry**;其他方法允许 null 值指定。 NULL 条目标识符被解释不同，具体取决于该对象。 例如，当调用**IAddrBook::OpenEntry**具有 NULL 条目标识符时，MAPI 打开通讯簿根容器。 消息存储库的**OpenEntry**方法的行为类似;打开的邮件存储区的根文件夹。 **IMAPIContainer::OpenEntry**，由文件夹和通讯簿容器实现可能返回 MAPI_E_INVALID_PARAMETER 或根容器，具体取决于实施。 
  
不允许 NULL 值的项标识符，除了会话的**OpenEntry**方法从其他**OpenEntry**方法不同，因为其作业是不打开对象。 相反，它探讨的项标识符，并将转发对实现适当的服务提供商的另一个**OpenEntry**方法的调用。 例如，如果具有一条消息的项标识符调用**IMAPISession::OpenEntry** ，MAPI 调用的**IMSLogon::OpenEntry**方法的消息存储负责邮件。 
  
除了使用会话打开对象时，客户端使用它对它们进行比较。 [IMAPISession::CompareEntryIDs](imapisession-compareentryids.md)方法通过比较其条目标识符比较对象。 如果包含的项标识符的[MAPIUID](mapiuid.md)结构属于同一服务提供商，MAPI 转发到该提供程序的调用。 两个条目标识符不匹配时， **CompareEntryIDs**将返回错误值。 尽管此方法可以将条目标识符属于任何类型的对象进行比较， **CompareEntryIDs**最适用于邮件存储通讯簿容器等更高级的对象。 要比较较低级别的对象，直接比较对象的搜索键 (**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))) 或记录键 (**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)))。 
  
**OpenEntry**，如**CompareEntryIDs**由多个对象实现。 选择使用有关的对象必须信息量根据要打开或比较哪种**OpenEntry**和**CompareEntryID**方法。 决定要调用的接口方法时，请使用以下准则： 
  
- 如果您没有任何信息有关的目标对象，调用[IMAPISession::OpenEntry](imapisession-openentry.md)或[IMAPISession::CompareEntryIDs](imapisession-compareentryids.md)。 此方法允许访问任何对象，但最慢的三个。
    
- 如果您知道目标对象的通讯簿条目而不是，例如，文件夹，调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)或[IAddrBook::CompareEntryIDs](iaddrbook-compareentryids.md)方法。 **IAddrBook::OpenEntry** NULL 指定为目标对象时打开通讯簿根的容器。 此方法使任意地址簿对象的访问权，并且比使用**IMAPISession**，但比使用**IMAPIContainer**慢。
    
- 如果正在使用的项标识符是短期条目标识符，或者如果您知道目标对象属于某个特定的通讯簿容器或文件夹，调用[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)方法。 此方法生成的最快的性能，但允许仅对特定的容器或文件夹中的对象的访问。 
    

