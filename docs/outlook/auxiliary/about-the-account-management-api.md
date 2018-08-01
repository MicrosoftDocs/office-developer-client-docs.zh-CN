---
title: 关于帐户管理 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: eb6b921d-ecf8-3ce5-87ba-ac1632416b05
description: 帐户管理 API 提供访问帐户信息，并支持帐户更改的通知。 此 api 的客户端，为邮件提供程序执行以下操作：
ms.openlocfilehash: 678143def25395c47f1c17cc99dcdcd1fb145e1c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774166"
---
# <a name="about-the-account-management-api"></a>关于帐户管理 API

帐户管理 API 提供访问帐户信息，并支持帐户更改的通知。 此 api 的客户端，为邮件提供程序执行以下操作：
  
1. 使用[IOlkAccountManager](iolkaccountmanager.md)管理帐户的访问权并设置有关帐户更改的通知。 
    
2. 实现和使用[IOlkAccountNotify](iolkaccountnotify.md)发送有关帐户更改的通知。 
    
3. 使用[IOlkEnum](iolkenum.md)枚举帐户。 
    
4. 使用[IOlkAccount](iolkaccount.md)可获取和设置属性和帐户的其他信息。 客户端获取[IOlkAccountManager::FindAccount](iolkaccountmanager-findaccount.md)或[IOlkEnum::GetNext](iolkenum-getnext.md)访问个人帐户通过该接口。 
    
5. 实现和使用[IOlkAccountHelper](iolkaccounthelper.md)提供帐户管理器帮助程序功能，包括帐户配置文件的名称和当前的 MAPI 会话。 
    
6. 实现和使用[IOlkErrorUnknown](iolkerrorunknown.md)提供有关在**IOlkAccountManager**、 **IOlkAccountNotify**和**IOlkAccount**错误的额外信息。 

##  <a name="account-management-api-components"></a>帐户管理 API 组件

帐户管理 API 提供了以下定义数据类型、 接口、 名为属性和属性。
  
### <a name="definitions"></a>定义
  
- [常量 （帐户管理 API）](constants-account-management-api.md)
    
### <a name="data-types"></a>数据类型
  
- [ACCT_BIN](acct_bin.md)
    
- [ACCT_VARIANT](acct_variant.md)
    
### <a name="interfaces"></a>接口
  
- [IOlkAccount](iolkaccount.md)
    
- [IOlkAccountHelper](iolkaccounthelper.md)
    
- [IOlkAccountManager](iolkaccountmanager.md)
    
- [IOlkAccountNotify](iolkaccountnotify.md)
    
- [IOlkEnum](iolkenum.md)
    
- [IOlkErrorUnknown](iolkerrorunknown.md)
    
### <a name="named-properties"></a>命名属性
  
- [PidLidInternetAccountName](pidlidinternetaccountname.md)
    
- [PidLidInternetAccountStamp](pidlidinternetaccountstamp.md)
    
### <a name="properties"></a>属性
  
- [PidTagNextSendAcct](pidtagnextsendacct.md)
    
- [PidTagPrimarySendAccount](pidtagprimarysendaccount.md)
    
- [PROP_ACCT_DELIVERY_FOLDER](prop_acct_delivery_folder.md)
    
- [PROP_ACCT_DELIVERY_STORE](prop_acct_delivery_store.md)
    
- [PROP_ACCT_ID](prop_acct_id.md)
    
- [PROP_ACCT_IS_EXCH](prop_acct_is_exch.md)
    
- [PROP_ACCT_NAME](prop_acct_name.md)
    
- [PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md)
    
- [PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md)
    
- [PROP_ACCT_SENTITEMS_EID](prop_acct_sentitems_eid.md)
    
- [PROP_ACCT_STAMP](prop_acct_stamp.md)
    
- [PROP_ACCT_USER_EMAIL_ADDR](prop_acct_user_email_addr.md)
    
- [PROP_ACCT_USER_DISPLAY_NAME](prop_acct_user_display_name.md)
    
- [PROP_MAPI_EMSMDB_UID](prop_mapi_emsmdb_uid.md)
    
- [PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md)
    
- [PROP_MAPI_TRANSPORT_FLAGS](prop_mapi_transport_flags.md)
    

