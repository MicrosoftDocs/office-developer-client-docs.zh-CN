---
title: PROP_SMTP_SSL
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: f46e8aa3-d2c2-45a2-93fe-1c40107fbf16
description: 指定是否对 SMTP 帐户使用安全套接字层 (SSL) 协议。
ms.openlocfilehash: 64856322ec0afce80777417f781c22b927ed5e2d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328306"
---
# <a name="propsmtpssl"></a>PROP_SMTP_SSL

指定是否对 SMTP 帐户使用安全套接字层 (SSL) 协议。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|标识符:  <br/> |0x0202  <br/> |
|属性类型  <br/> |PT_DWORD  <br/> |
|属性标记：  <br/> |0x02020003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>注解

零值表示不使用 ssl 加密, 否则使用 ssl 加密。
  
## <a name="see-also"></a>另请参阅

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

