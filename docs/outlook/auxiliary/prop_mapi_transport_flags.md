---
title: PROP_MAPI_TRANSPORT_FLAGS
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 12cfe096-6882-c0be-b248-87567cb71e83
description: 表示 Outlook 用于确定必要的同步任务并禁用该帐户不支持的用户界面 (UI) 元素的传输设置。
ms.openlocfilehash: 707306c3bfbeebdd18f82bacfc121274be08aa50
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326479"
---
# <a name="propmapitransportflags"></a>PROP_MAPI_TRANSPORT_FLAGS

表示 Outlook 用于确定必要的同步任务并禁用该帐户不支持的用户界面 (UI) 元素的传输设置。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x2010  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x20100102  <br/> |
|访问权限  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>注解

Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.
  
如果帐户只能发送邮件, 但无法接收邮件, 则返回**MAPIACCT_SEND_ONLY** 。 在这种情况下, Outlook 禁用不适用于此类帐户的 ui (例如, 用于 "**发送/接收**" 的 ui)。
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)

