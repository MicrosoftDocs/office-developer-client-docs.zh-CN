---
title: PROP_SMTP_AUTH_METHOD
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 4202cafc-9011-406d-90b3-8dabf531c90b
description: 指定要用于 SMTP 帐户的身份验证方法。
ms.openlocfilehash: bb5adeb1fe73ed8b7ab69ca584215b44e1a9e4b7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434639"
---
# <a name="propsmtpauthmethod"></a>PROP_SMTP_AUTH_METHOD

指定要用于 SMTP 帐户的身份验证方法。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标识符:  <br/> |0x0208  <br/> |
|属性类型  <br/> |PT_DWORD  <br/> |
|属性标记：  <br/> |0x02080003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

该值是以下常量的位掩码。 有关其值, 请参阅[常量 (帐户管理 API)](constants-account-management-api.md) 。 
  
- **SMTP_AUTH_SAME_AS_POP**意味着使用与我的传入邮件服务器相同的凭据, 如[PROP_INET_USER](prop_inet_user.md)和[PROP_INET_PASSWORD](prop_inet_password.md)提供的一样。
    
- **SMTP_AUTH_USER_PASS**是指使用[PROP_SMTP_USER](prop_smtp_user.md)和[PROP_SMTP_PASSWORD](prop_smtp_password.md)提供的凭据。
    
- **SMTP_AUTH_RECEIVE_BEFORE_SEND**意味着请求用户在发送邮件之前登录到传入邮件服务器。 
    
## <a name="see-also"></a>另请参阅

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)

