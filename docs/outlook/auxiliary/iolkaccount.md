---
title: IOlkAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b7cb295-fc77-a8b9-aac9-e548f3b4afcb
ms.openlocfilehash: dc802d8fef0d90672428c8bfa3662a2734637d05
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774314"
---
# <a name="iolkaccount"></a>IOlkAccount

获取和设置的属性和帐户的其他信息的支持。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IOlkErrorUnknown](iolkerrorunknown.md) <br/> |
|通过实现：  <br/> |Outlook  <br/> |
|提供者：  <br/> |[IOlkAccountManager::FindAccount](iolkaccountmanager-findaccount.md)和[IOlkEnum::GetNext](iolkenum-getnext.md) <br/> |
|调用：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IOlkAccount  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
|[GetAccountInfo](iolkaccount-getaccountinfo.md) <br/> |获取的类型和类别的指定的帐户。  <br/> |
|[GetProp](iolkaccount-getprop.md) <br/> |获取指定的帐户属性的值。 请参阅下面的属性表。  <br/> |
|[SetProp](iolkaccount-setprop.md) <br/> |设置指定的帐户属性的值。 请参阅下面的属性表。  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
|[FreeMemory](iolkaccount-freememory.md) <br/> |释放内存分配**IOlkAccount**接口。  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
|[SaveChanges](iolkaccount-savechanges.md) <br/> |将更改提交给 account 对象，通过写入注册表存储。  <br/> |
   
## <a name="properties"></a>属性

|||
|:-----|:-----|
|[PROP_ACCT_DELIVERY_FOLDER](prop_acct_delivery_folder.md) <br/> |表示该帐户的默认送达文件夹的条目 ID。  <br/> |
|[PROP_ACCT_DELIVERY_STORE](prop_acct_delivery_store.md) <br/> |表示默认送达存储的帐户的条目 ID。  <br/> |
|[PROP_ACCT_ID](prop_acct_id.md) <br/> |返回在 Outlook 2000 和早期版本的 Outlook 帐户标识符。  <br/> |
|[PROP_ACCT_IS_EXCH](prop_acct_is_exch.md) <br/> |如果该帐户是 Microsoft Exchange 帐户，则为 true。  <br/> |
|[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md) <br/> |以来 Outlook 2002 的 Outlook 版本中返回的帐户标识符。  <br/> |
|[PROP_ACCT_NAME](prop_acct_name.md) <br/> |返回的帐户名称。  <br/> |
|[PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md) <br/> |检索存储的帐户首选项配置文件一节的唯一标识符 (UID)。  <br/> |
|[PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md) <br/> |返回的帐户"发送"戳。  <br/> |
|[PROP_ACCT_SENTITEMS_EID](prop_acct_sentitems_eid.md) <br/> |表示的帐户已发送邮件的默认文件夹的条目 ID。  <br/> |
|[PROP_ACCT_STAMP](prop_acct_stamp.md) <br/> |返回帐户戳。  <br/> |
|[PROP_ACCT_USER_DISPLAY_NAME](prop_acct_user_display_name.md) <br/> |返回的用户显示名称。  <br/> |
|[PROP_ACCT_USER_EMAIL_ADDR](prop_acct_user_email_addr.md) <br/> |指定的帐户的电子邮件地址。  <br/> |
|[PROP_MAPI_EMSMDB_UID](prop_mapi_emsmdb_uid.md) <br/> |表示包含 Exchange 帐户的 UID [ACCT_BIN](acct_bin.md)结构。  <br/> |
|[PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md) <br/> |检索或设置的帐户的地址簿条目 ID。  <br/> |
|[PROP_MAPI_TRANSPORT_FLAGS](prop_mapi_transport_flags.md) <br/> |表示 Microsoft Outlook 使用以确定所需同步任务，并禁用该帐户不支持的用户界面 (UI) 元素的传输设置。  <br/> |
   
## <a name="remarks"></a>说明

搜索时获取枚举中的下一个帐户，支持**IOlkAccount**和**IOlkEnum::GetNext**帐户时，由**IOlkAccountManager::FindAccount**返回此接口。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)

