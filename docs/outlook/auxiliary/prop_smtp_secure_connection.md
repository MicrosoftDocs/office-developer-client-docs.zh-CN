---
title: PROP_SMTP_SECURE_CONNECTION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e316a424-d789-4ce5-bcc6-263049f3659e
description: 指定要用于 SMTP 帐户的加密连接的类型。
ms.openlocfilehash: 67eae5c9c5ca1b7f664ceaac0463ef3f3c9a291a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421282"
---
# <a name="prop_smtp_secure_connection"></a>PROP_SMTP_SECURE_CONNECTION

指定要用于 SMTP 帐户的加密连接的类型。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标识符:  <br/> |0x020A  <br/> |
|属性类型  <br/> |PT_DWORD  <br/> |
|属性标记：  <br/> |0x020A0003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>备注

值可以是下列常量之一。 请参阅 [Constants (Account management API) ](constants-account-management-api.md) 了解其值。 
  
|**Constants**|**说明**|
|:-----|:-----|
|**ENCRYPT_CONN_NO_SECURITY** <br/> |请勿使用任何加密。  <br/> |
|**ENCRYPT_CONN_SSL** <br/> |使用安全套接字层 (SSL) 加密。  <br/> |
|**ENCRYPT_CONN_TLS** <br/> |使用传输层安全性 (TLS) 加密和身份验证协议。  <br/> |
|**ENCRYPT_CONN_AUTO** <br/> |自动检测和使用邮件服务器支持的加密方法。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

