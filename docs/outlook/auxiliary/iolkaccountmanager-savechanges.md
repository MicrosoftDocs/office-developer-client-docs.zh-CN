---
title: IOlkAccountManagerSaveChanges
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 32a5d4b7-ead7-24e7-58f2-750232263a0d
description: 保存对指定帐户的更改。
ms.openlocfilehash: dbb1dffa1725e96bd2ab635341718ce53738b864
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429605"
---
# <a name="iolkaccountmanagersavechanges"></a>IOlkAccountManager::SaveChanges

保存对指定帐户的更改。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccountManager](iolkaccountmanager.md).
  
```cpp
HRESULT IOlkAccountManager::SaveChanges (  
    DWORD dwAcctID, 
    DWORD dwFlags 
); 
```

## <a name="parameters"></a>参数

_dwAcctID_
  
> [in]要保存的帐户 ID。 
    
_dwFlags_
  
> [] in若要修改行为的标志。 OLK_ACCOUNT_NO_FLAGS是唯一受支持的值。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功  <br/> |
|E_ACCT_NOT_FOUND  <br/> |找不到指定的帐户。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
   
## <a name="remarks"></a>备注

使用 [IOlkAccount：：SetProp](iolkaccount-setprop.md)更改帐户属性的值后，使用 **IOlkAccountManager：：SaveChanges** 或 [IOlkAccount：：SaveChanges](iolkaccount-savechanges.md) 保存此类更改。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md) 
- [IOlkAccount::SaveChanges](iolkaccount-savechanges.md)

