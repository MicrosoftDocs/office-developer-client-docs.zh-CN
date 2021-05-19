---
title: 属性 （帐户管理 API）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: a5204ddd-5af4-4dd8-bc83-af96ac390786
description: 本部分介绍帐户管理 API 中的属性。
ms.openlocfilehash: d0b8c06716bd2f3a3bb2941e098bd9f11ab87183
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416333"
---
# <a name="properties-account-management-api"></a>属性 （帐户管理 API）

本部分介绍帐户管理 API 中的属性。
  
|**属性**|**说明**|
|:-----|:-----|
|[PidTagNextSendAcct](pidtagnextsendacct.md) <br/> |这是邮件的辅助帐户"发送"标记。  <br/> |
|[PidTagPrimarySendAccount](pidtagprimarysendaccount.md) <br/> |这是邮件的主帐户"发送"标记。  <br/> |
|[PROP_ACCT_DELIVERY_FOLDER](prop_acct_delivery_folder.md) <br/> |表示该帐户的默认送达文件夹的条目 ID。  <br/> |
|[PROP_ACCT_DELIVERY_STORE](prop_acct_delivery_store.md) <br/> |表示帐户的默认送达存储的条目 ID。  <br/> |
|[PROP_ACCT_ID](prop_acct_id.md) <br/> |返回一个唯一标识创建帐户的配置文件中的帐户的标识符。  <br/> |
|[PROP_ACCT_IS_EXCH](prop_acct_is_exch.md) <br/> |如此 如果该帐户是一个Exchange帐户。  <br/> |
|[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md) <br/> |返回跨配置文件唯一Outlook标识符。  <br/> |
|[PROP_ACCT_NAME](prop_acct_name.md) <br/> |返回或设置帐户名称。  <br/> |
|[PROP_ACCT_PREFERENCES_UID](prop_acct_preferences_uid.md) <br/> |检索存储帐户首选项 (配置文件) UID 对象的唯一标识符。  <br/> |
|[PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md) <br/> |返回帐户"send"标记。  <br/> |
|[PROP_ACCT_SENTITEMS_EID](prop_acct_sentitems_eid.md) <br/> |表示帐户已发送项目的默认文件夹的条目 ID。  <br/> |
|[PROP_ACCT_STAMP](prop_acct_stamp.md) <br/> |返回帐户标记。  <br/> |
|[PROP_ACCT_USER_EMAIL_ADDR](prop_acct_user_email_addr.md) <br/> |指定帐户的电子邮件地址。  <br/> |
|[PROP_ACCT_USER_DISPLAY_NAME](prop_acct_user_display_name.md) <br/> |返回或设置用户显示名称。  <br/> |
|[PROP_INET_PASSWORD](prop_inet_password.md) <br/> |表示常规 Internet 邮箱的用户密码。  <br/> |
|[PROP_INET_PORT](prop_inet_port.md) <br/> |代表常规 Internet 邮箱的端口号。  <br/> |
|[PROP_INET_SERVER](prop_inet_server.md) <br/> |表示常规 Internet 邮箱的服务器名称。  <br/> |
|[PROP_INET_SSL](prop_inet_ssl.md) <br/> |指定安全套接字层 (SSL) 是否应用于常规 Internet 邮箱。  <br/> |
|[PROP_INET_USE_SPA](prop_inet_use_spa.md) <br/> |指定 SPA 邮箱 (密码) 安全密码身份验证是否应用于常规 Internet 邮箱。  <br/> |
|[PROP_INET_USER](prop_inet_user.md) <br/> |表示常规 Internet 邮箱的用户名。  <br/> |
|[PROP_MAPI_EMSMDB_UID](prop_mapi_emsmdb_uid.md) <br/> |表示[ACCT_BIN](acct_bin.md)帐户的 UID 的 Exchange 结构。  <br/> |
|[PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md) <br/> |检索或设置帐户的通讯簿条目 ID。  <br/> |
|[PROP_MAPI_TRANSPORT_FLAGS](prop_mapi_transport_flags.md) <br/> |表示传输设置Outlook用于确定必要的同步任务，以及禁用用户界面 (UI) 帐户不支持的元素。  <br/> |
|[PROP_POP_LEAVE_ON_SERVER](prop_pop_leave_on_server.md) <br/> |指定在服务器上为 POP 帐户保留邮件的副本。  <br/> |
|[PROP_SMTP_AUTH_METHOD](prop_smtp_auth_method.md) <br/> |指定要用于 SMTP 帐户的身份验证方法。  <br/> |
|[PROP_SMTP_PASSWORD](prop_smtp_password.md) <br/> |表示 SMTP 帐户的密码。  <br/> |
|[PROP_SMTP_PORT](prop_smtp_port.md) <br/> |表示 SMTP 帐户的端口号。  <br/> |
|[PROP_SMTP_SECURE_CONNECTION](prop_smtp_secure_connection.md) <br/> |指定要用于 SMTP 帐户的加密连接的类型。  <br/> |
|[PROP_SMTP_SERVER](prop_smtp_server.md) <br/> |表示 SMTP 帐户的服务器名称。  <br/> |
|[PROP_SMTP_SSL](prop_smtp_ssl.md) <br/> |指定是否对 SMTP 帐户 (SSL) 安全套接字层协议。  <br/> |
|[PROP_SMTP_USE_AUTH](prop_smtp_use_auth.md) <br/> |指定是否对 SMTP 帐户使用身份验证。  <br/> |
|[PROP_SMTP_USE_SPA](prop_smtp_use_spa.md) <br/> |指定是否对 SMTP 帐户 (SPA) 安全密码身份验证。  <br/> |
|[PROP_SMTP_USER](prop_smtp_user.md) <br/> |表示 SMTP 帐户的用户名。  <br/> |
   

