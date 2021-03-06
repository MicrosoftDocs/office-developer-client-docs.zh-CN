---
title: IOlkAccountManagerAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c88f087e-4ff4-0837-186d-b6e761468a4d
description: 向帐户管理员注册客户端，以接收有关所有帐户的通知。
ms.openlocfilehash: 5460d55d906d382ce40ecd3fd9277cf370295680
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427708"
---
# <a name="iolkaccountmanageradvise"></a>IOlkAccountManager::Advise

向帐户管理员注册客户端，以接收有关所有帐户的通知。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccountManager](iolkaccountmanager.md).
  
```cpp
HRESULT IOlkAccountManager::Advise (  
    IOlkAccountNotify *pNotify, 
    DWORD *pdwCookie 
);
```

## <a name="parameters"></a>参数

_pNotify_
  
> [in]帐户管理员用于向客户端发送通知的 [IOlkAccountNotify](iolkaccountnotify.md) 接口。 
    
_pdwCookie_
  
> [out] [IOlkAccountManager：：Unadvise](iolkaccountmanager-unadvise.md) 在删除帐户注册时将使用的 Cookie。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_INVALIDARG  <br/> |提供了无效的参数。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccountManager::Unadvise](iolkaccountmanager-unadvise.md)

