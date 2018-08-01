---
title: IOlkAccountManagerGetOrder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bd22026c-e4f7-2f25-0ef2-5d9539fd7eee
description: 获取指定的类别的帐户的顺序。
ms.openlocfilehash: d05e354e25d49a51b3d3f8f053c2b39dc37b333f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774345"
---
# <a name="iolkaccountmanagergetorder"></a>IOlkAccountManager::GetOrder

获取指定的类别的帐户的顺序。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkAccountManager](iolkaccountmanager.md)
  
```cpp
HRESULT IOlkAccountManager::GetOrder (  
    const CLSID *pclsidCategory, 
    DWORD *pcAccts, 
    DWORD *prgAccts[] 
); 
```

## <a name="parameters"></a>参数

_pclsidCategory_
  
> [in]类别类 ID 为其获取顺序。 该值必须为以下项之一：
    
   - CLSID_OlkMail
    
   - CLSID_OlkAddressBook
    
   - CLSID_OlkStore
    
_pcAccts_
  
>  [输出]帐户数。 
    
_prgAccts_
  
> [输出]一个指向帐户的数组。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |成功呼叫  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
   
## <a name="remarks"></a>注解

调用此方法之前，呼叫者在哪些*prgAccts*点数组分配仅数组指针*prgAccts*但没有内存。 此方法返回后，呼叫者必须使用[IOlkAccountManager::FreeMemory](iolkaccountmanager-freememory.md)版本为*prgAccts*分配的内存。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccountManager::SetOrder](iolkaccountmanager-setorder.md)

