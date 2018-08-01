---
title: IOlkAccountNotifyNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dbce1c47-1252-ddeb-64ae-d52118e6821f
description: 通知客户端到指定的帐户的更改。
ms.openlocfilehash: ea4cab8cb8571cf5f34637c08935c78c657e5503
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774358"
---
# <a name="iolkaccountnotifynotify"></a>IOlkAccountNotify::Notify

通知客户端到指定的帐户的更改。
  
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
  
> [in]通知的类型。 该值必须为以下项之一：
    
   - NOTIFY_ACCT_CHANGED 
    
   - NOTIFY_ACCT_CREATED 
    
   - NOTIFY_ACCT_DELETED
    
   - NOTIFY_ACCT_ORDER_CHANGED 
    
   - NOTIFY_ACCT_PREDELETED 
    
 _dwAcctID_
  
> [in]已创建，更改的帐户的帐户 ID 删除，或者前删除。
    
 _dwFlags_
  
>  [in]不使用。 OLK_ACCOUNT_NO_FLAGS 是唯一受支持的值。 
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccountManager](iolkaccountmanager.md)

