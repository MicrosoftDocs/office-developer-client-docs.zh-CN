---
title: IOlkAccountNotify
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 360854bb-e9be-a784-e80b-3f18418ded1b
ms.openlocfilehash: ab24feca84e7049a9800b860c332db52d19cf929
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322069"
---
# <a name="iolkaccountnotify"></a>IOlkAccountNotify

为客户端提供对帐户更改的回调。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自:  <br/> |[IOlkErrorUnknown](iolkerrorunknown.md) <br/> |
|提供者：  <br/> | 客户端  <br/> |
|接口标识符:  <br/> |IID_IOlkAccountNotify  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[Notify](iolkaccountnotify-notify.md) <br/> |通知客户端对指定帐户所做的更改。  <br/> |
   
## <a name="remarks"></a>注解

在设置通知时, 此接口将传递给[IOlkAccountManager:: Advise](iolkaccountmanager-advise.md) 。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

