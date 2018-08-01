---
title: PROP_SMTP_SECURE_CONNECTION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e316a424-d789-4ce5-bcc6-263049f3659e
description: 指定的加密连接使用的 SMTP 帐户的类型。
ms.openlocfilehash: e1c8c8dacf953407d4cbb114aa5ee0a4cdb6acf5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774448"
---
# <a name="propsmtpsecureconnection"></a>PROP_SMTP_SECURE_CONNECTION

指定的加密连接使用的 SMTP 帐户的类型。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标识符：  <br/> |0x020A  <br/> |
|属性类型  <br/> |PT_DWORD  <br/> |
|属性标记：  <br/> |0x020A0003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

值可以是以下常量之一。 其值，请参阅[常量 （帐户管理 API）](constants-account-management-api.md) 。 
  
|**常量**|**说明**|
|:-----|:-----|
|**ENCRYPT_CONN_NO_SECURITY** <br/> |不使用任何加密。  <br/> |
|**ENCRYPT_CONN_SSL** <br/> |使用安全套接字层 (SSL) 加密。  <br/> |
|**ENCRYPT_CONN_TLS** <br/> |使用传输层安全性 (TLS) 加密和身份验证协议。  <br/> |
|**ENCRYPT_CONN_AUTO** <br/> |自动检测并使用支持的邮件服务器的加密方法。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

