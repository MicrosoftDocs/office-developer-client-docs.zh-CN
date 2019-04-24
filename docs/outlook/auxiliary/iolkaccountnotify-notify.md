---
title: IOlkAccountNotifyNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dbce1c47-1252-ddeb-64ae-d52118e6821f
description: 通知客户端对指定帐户所做的更改。
ms.openlocfilehash: 269d8a8bd605c9d8a0a4057e87895522d8587ee9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321964"
---
# <a name="iolkaccountnotifynotify"></a>IOlkAccountNotify::Notify

通知客户端对指定帐户所做的更改。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkAccountNotify](iolkaccountnotify.md)。
  
```cpp
HRESULT IOlkAccount::Notify(  
    DWORD dwNotify, 
    DWORD dwAcctID, 
    DWORD dwFlags 
);

```

## <a name="parameters"></a>参数

_dwNotify_
  
> 实时通知的类型。 值必须为以下值之一：
    
   - NOTIFY_ACCT_CHANGED 
    
   - NOTIFY_ACCT_CREATED 
    
   - NOTIFY_ACCT_DELETED
    
   - NOTIFY_ACCT_ORDER_CHANGED 
    
   - NOTIFY_ACCT_PREDELETED 
    
 _dwAcctID_
  
> 实时已创建、更改、删除或预删除的帐户的帐户 ID。
    
 _dwFlags_
  
>  实时不使用。 OLK_ACCOUNT_NO_FLAGS 是唯一受支持的值。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccountManager](iolkaccountmanager.md)

