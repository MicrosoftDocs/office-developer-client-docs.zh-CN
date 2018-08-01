---
title: IOlkAccountNotify
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 360854bb-e9be-a784-e80b-3f18418ded1b
ms.openlocfilehash: f4b57ad1062df9aa1809e8eb422a2c983adcac4a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774357"
---
# <a name="iolkaccountnotify"></a>IOlkAccountNotify

为帐户的更改到客户端提供回调。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IOlkErrorUnknown](iolkerrorunknown.md) <br/> |
|提供者：  <br/> | 客户端  <br/> |
|接口标识符：  <br/> |IID_IOlkAccountNotify  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[Notify](iolkaccountnotify-notify.md) <br/> |通知客户端到指定的帐户的更改。  <br/> |
   
## <a name="remarks"></a>说明

设置通知时，该接口被传递给[IOlkAccountManager::Advise](iolkaccountmanager-advise.md) 。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

