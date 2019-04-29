---
title: IOlkAccountSaveChanges
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8f1ab61e-7d1c-50d5-ae21-8cb4b08d729c
description: 通过写入注册表存储提交对 account 对象所做的更改。
ms.openlocfilehash: c23cefbbda62de9b7e159e500d95b8db5ff34ef4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425832"
---
# <a name="iolkaccountsavechanges"></a>IOlkAccount::SaveChanges

通过写入注册表存储提交对 account 对象所做的更改。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
```cpp
HRESULT IOlkAccount::SaveChanges (  
    DWORD dwFlags 
); 
```

## <a name="parameters"></a>参数

_dwFlags_
  
> [] in若要修改行为的标志。 OLK_ACCOUNT_NO_FLAGS 是唯一受支持的值。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |方法已成功。  <br/> |
|E_ACCT_NOT_FOUND  <br/> |找不到指定的帐户。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
   
## <a name="remarks"></a>说明

使用[IOlkAccount:: SetProp](iolkaccount-setprop.md)更改 account 属性的值后, 请使用**IOlkAccount:: SaveChanges**保存此类更改。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md) 
- [IOlkAccountManager::SaveChanges](iolkaccountmanager-savechanges.md)

