---
title: IOlkAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b7cb295-fc77-a8b9-aac9-e548f3b4afcb
ms.openlocfilehash: 007a44d13565889b4775f2d3fe9979685e1878b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425062"
---
# <a name="iolkaccount"></a>IOlkAccount

支持获取和设置属性以及帐户的其他信息。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自：  <br/> |[IOlkErrorUnknown](iolkerrorunknown.md) <br/> |
|实现者：  <br/> |Outlook  <br/> |
|提供者：  <br/> |[IOlkAccountManager：：FindAccount](iolkaccountmanager-findaccount.md) 和 [IOlkEnum：：GetNext](iolkenum-getnext.md) <br/> |
|调用者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IOlkAccount  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
|[GetAccountInfo](iolkaccount-getaccountinfo.md) <br/> |获取指定帐户的类型和类别。  <br/> |
|[GetProp](iolkaccount-getprop.md) <br/> |获取指定帐户属性的值。 请参阅下面的"属性"表。  <br/> |
|[SetProp](iolkaccount-setprop.md) <br/> |设置指定帐户属性的值。 请参阅下面的"属性"表。  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
|[FreeMemory](iolkaccount-freememory.md) <br/> |释放由 **IOlkAccount** 接口分配的内存。  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
|[SaveChanges](iolkaccount-savechanges.md) <br/> |通过写入注册表存储来提交对帐户对象的更改。  <br/> |
   
## <a name="properties"></a>属性

|||
|:-----|:-----|
|[PROP_ACCT_DELIVERY_FOLDER](prop_acct_delivery_folder.md) <br/> |表示该帐户的默认送达文件夹的条目 ID。  <br/> |
|[PROP_ACCT_DELIVERY_STORE](prop_acct_delivery_store.md) <br/> |表示帐户的默认送达存储的条目 ID。  <br/> |
|[PROP_ACCT_ID](prop_acct_id.md) <br/> |返回 Outlook 2000 及早期版本的 Outlook。  <br/> |
|[PROP_ACCT_IS_EXCH](prop_acct_is_exch.md) <br/> |如此 如果该帐户是 Microsoft Exchange帐户。  <br/> |
|[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md) <br/> |返回自 2002 Outlook以来Outlook帐户标识符。  <br/> |
|[PROP_ACCT_NAME](prop_acct_name.md) <br/> |返回帐户名称。  <br/> |
|[PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md) <br/> |检索存储帐户首选项 (配置文件) UID 对象的唯一标识符。  <br/> |
|[PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md) <br/> |返回帐户"send"标记。  <br/> |
|[PROP_ACCT_SENTITEMS_EID](prop_acct_sentitems_eid.md) <br/> |表示帐户已发送项目的默认文件夹的条目 ID。  <br/> |
|[PROP_ACCT_STAMP](prop_acct_stamp.md) <br/> |返回帐户标记。  <br/> |
|[PROP_ACCT_USER_DISPLAY_NAME](prop_acct_user_display_name.md) <br/> |返回用户显示名称。  <br/> |
|[PROP_ACCT_USER_EMAIL_ADDR](prop_acct_user_email_addr.md) <br/> |指定帐户的电子邮件地址。  <br/> |
|[PROP_MAPI_EMSMDB_UID](prop_mapi_emsmdb_uid.md) <br/> |表示[ACCT_BIN](acct_bin.md)帐户的 UID 的 Exchange 结构。  <br/> |
|[PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md) <br/> |检索或设置帐户的通讯簿条目 ID。  <br/> |
|[PROP_MAPI_TRANSPORT_FLAGS](prop_mapi_transport_flags.md) <br/> |表示 Microsoft Outlook用于确定必要的同步任务和禁用用户界面 (UI) 帐户不支持的元素的传输设置。  <br/> |
   
## <a name="remarks"></a>备注

当在枚举器中查找支持 **IOlkAccount** 和 **IOlkEnum：：GetNext** 的帐户时 **，IOlkAccountManager：：FindAccount** 将返回此接口。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)

