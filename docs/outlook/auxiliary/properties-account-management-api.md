---
title: 属性 （帐户管理 API）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: a5204ddd-5af4-4dd8-bc83-af96ac390786
description: 本节介绍帐户管理 API 中的属性。
ms.openlocfilehash: abf7422d941f581f66a118c35d2b6ff3c03e8b6b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774478"
---
# <a name="properties-account-management-api"></a>属性 （帐户管理 API）

本节介绍帐户管理 API 中的属性。
  
|**属性**|**说明**|
|:-----|:-----|
|[PidTagNextSendAcct](pidtagnextsendacct.md) <br/> |这是辅助帐户"发送"戳的邮件。  <br/> |
|[PidTagPrimarySendAccount](pidtagprimarysendaccount.md) <br/> |这是一条消息的主帐户"发送"戳。  <br/> |
|[PROP_ACCT_DELIVERY_FOLDER](prop_acct_delivery_folder.md) <br/> |表示该帐户的默认送达文件夹的条目 ID。  <br/> |
|[PROP_ACCT_DELIVERY_STORE](prop_acct_delivery_store.md) <br/> |表示默认送达存储的帐户的条目 ID。  <br/> |
|[PROP_ACCT_ID](prop_acct_id.md) <br/> |返回一个唯一标识在其中创建该帐户的配置文件中的帐户的标识符。  <br/> |
|[PROP_ACCT_IS_EXCH](prop_acct_is_exch.md) <br/> |如果该帐户是 Exchange 帐户，则为 true。  <br/> |
|[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md) <br/> |返回 Outlook 配置文件之间都是唯一的帐户标识符。  <br/> |
|[PROP_ACCT_NAME](prop_acct_name.md) <br/> |返回或设置的帐户名称。  <br/> |
|[PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md) <br/> |检索存储的帐户首选项配置文件一节的唯一标识符 (UID)。  <br/> |
|[PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md) <br/> |返回的帐户"发送"戳。  <br/> |
|[PROP_ACCT_SENTITEMS_EID](prop_acct_sentitems_eid.md) <br/> |表示的帐户已发送邮件的默认文件夹的条目 ID。  <br/> |
|[PROP_ACCT_STAMP](prop_acct_stamp.md) <br/> |返回帐户戳。  <br/> |
|[PROP_ACCT_USER_EMAIL_ADDR](prop_acct_user_email_addr.md) <br/> |指定的帐户的电子邮件地址。  <br/> |
|[PROP_ACCT_USER_DISPLAY_NAME](prop_acct_user_display_name.md) <br/> |返回或设置用户的显示名称。  <br/> |
|[PROP_INET_PASSWORD](prop_inet_password.md) <br/> |代表常规的 Internet 邮箱的用户密码。  <br/> |
|[PROP_INET_PORT](prop_inet_port.md) <br/> |代表常规 Internet 邮箱的端口号。  <br/> |
|[PROP_INET_SERVER](prop_inet_server.md) <br/> |代表常规的 Internet 邮箱的服务器名称。  <br/> |
|[PROP_INET_SSL](prop_inet_ssl.md) <br/> |指定是否应为常规 Internet 邮箱使用安全套接字层 (SSL)。  <br/> |
|[PROP_INET_USE_SPA](prop_inet_use_spa.md) <br/> |指定是否应为常规 Internet 邮箱使用安全密码身份验证 (SPA)。  <br/> |
|[PROP_INET_USER](prop_inet_user.md) <br/> |代表常规 Internet 邮箱的用户名。  <br/> |
|[PROP_MAPI_EMSMDB_UID](prop_mapi_emsmdb_uid.md) <br/> |表示包含 Exchange 帐户的 UID [ACCT_BIN](acct_bin.md)结构。  <br/> |
|[PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md) <br/> |检索或设置的帐户的地址簿条目 ID。  <br/> |
|[PROP_MAPI_TRANSPORT_FLAGS](prop_mapi_transport_flags.md) <br/> |代表 Outlook 使用以确定所需同步任务，并禁用该帐户不支持的用户界面 (UI) 元素的传输设置。  <br/> |
|[PROP_POP_LEAVE_ON_SERVER](prop_pop_leave_on_server.md) <br/> |指定的 POP 帐户的服务器上保留邮件副本。  <br/> |
|[PROP_SMTP_AUTH_METHOD](prop_smtp_auth_method.md) <br/> |指定要使用的 SMTP 帐户的身份验证方法。  <br/> |
|[PROP_SMTP_PASSWORD](prop_smtp_password.md) <br/> |代表 SMTP 帐户的密码。  <br/> |
|[PROP_SMTP_PORT](prop_smtp_port.md) <br/> |代表 SMTP 帐户的端口号。  <br/> |
|[PROP_SMTP_SECURE_CONNECTION](prop_smtp_secure_connection.md) <br/> |指定的加密连接使用的 SMTP 帐户的类型。  <br/> |
|[PROP_SMTP_SERVER](prop_smtp_server.md) <br/> |代表 SMTP 帐户的服务器名称。  <br/> |
|[PROP_SMTP_SSL](prop_smtp_ssl.md) <br/> |指定是否使用安全套接字层 (SSL) 协议进行 SMTP 帐户。  <br/> |
|[PROP_SMTP_USE_AUTH](prop_smtp_use_auth.md) <br/> |指定是否使用的 SMTP 帐户身份验证。  <br/> |
|[PROP_SMTP_USE_SPA](prop_smtp_use_spa.md) <br/> |指定是否为 SMTP 帐户使用安全密码身份验证 (SPA)。  <br/> |
|[PROP_SMTP_USER](prop_smtp_user.md) <br/> |代表 SMTP 帐户的用户名。  <br/> |
   

