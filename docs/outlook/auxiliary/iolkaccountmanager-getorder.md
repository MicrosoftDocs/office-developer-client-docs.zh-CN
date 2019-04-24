---
title: IOlkAccountManagerGetOrder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bd22026c-e4f7-2f25-0ef2-5d9539fd7eee
description: 获取指定的帐户类别的排序。
ms.openlocfilehash: 3eb6dd96caa43f81eba86a389c938ef90c9533b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322027"
---
# <a name="iolkaccountmanagergetorder"></a>IOlkAccountManager::GetOrder

获取指定的帐户类别的排序。
  
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
  
> 实时要为其获取订单的类别类 ID。 该值必须为以下项之一：
    
   - CLSID_OlkMail
    
   - CLSID_OlkAddressBook
    
   - CLSID_OlkStore
    
_pcAccts_
  
>  排除帐户数。 
    
_prgAccts_
  
> 排除指向帐户数组的指针。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |呼叫成功  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
   
## <a name="remarks"></a>注解

调用此方法之前, 调用方仅分配一个数组指针*prgAccts* , 但在该数组处没有*prgAccts*点的内存。 此方法返回后, 调用方必须使用[IOlkAccountManager:: FreeMemory](iolkaccountmanager-freememory.md)来释放为*prgAccts*分配的内存。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccountManager::SetOrder](iolkaccountmanager-setorder.md)

