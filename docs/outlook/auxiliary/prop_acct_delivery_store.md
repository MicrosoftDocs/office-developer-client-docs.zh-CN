---
title: PROP_ACCT_DELIVERY_STORE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5db43e9-687b-d467-1be1-3737e3f91c27
description: 表示帐户的默认送达存储的条目 ID。
ms.openlocfilehash: d803c539ec99da4d7fb31063f48237788f3ac3d9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418895"
---
# <a name="prop_acct_delivery_store"></a>PROP_ACCT_DELIVERY_STORE

表示帐户的默认送达存储的条目 ID。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0018  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x00180102  <br/> |
|访问权限  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>备注

Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.
  
将应用商店设置为帐户的默认传递存储区的副作用之一是，在启动 Outlook 时，Outlook 会为存储区创建搜索文件夹（如果它们不存在的话）并列出 To-Do 栏中的存储区。
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)
- [常量 （帐户管理 API）](constants-account-management-api.md)

