---
title: PROP_MAPI_TRANSPORT_FLAGS
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 12cfe096-6882-c0be-b248-87567cb71e83
description: 代表 Outlook 使用以确定所需同步任务，并禁用该帐户不支持的用户界面 (UI) 元素的传输设置。
ms.openlocfilehash: 95b61ea994557be76303f8b9b0541353b6ed13f6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774438"
---
# <a name="propmapitransportflags"></a>PROP_MAPI_TRANSPORT_FLAGS

代表 Outlook 使用以确定所需同步任务，并禁用该帐户不支持的用户界面 (UI) 元素的传输设置。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x2010  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x20100102  <br/> |
|访问权限  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>备注

Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.
  
返回**MAPIACCT_SEND_ONLY** ，如果该帐户只能发送消息，但无法接收消息。 在这种情况下，Outlook 禁用不适用于这种类型的帐户 (例如，**发送/接收**的 UI) 的 UI。
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)

