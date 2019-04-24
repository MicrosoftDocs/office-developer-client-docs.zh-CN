---
title: IOlkAccountManagerSetOrder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e219adf6-e591-72e6-b9bd-2fc62eb5142d
description: 修改指定帐户类别的顺序。
ms.openlocfilehash: 29dfe4fd1bda9e323481297167361650c3b3a173
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322041"
---
# <a name="iolkaccountmanagersetorder"></a>IOlkAccountManager::SetOrder

修改指定帐户类别的顺序。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccountManager](iolkaccountmanager.md).
  
```cpp
HRESULT SetOrder(
    const CLSID * pclsidCategory,
    DWORD cAccts,
    DWORD rgAccts[]
);

```

## <a name="parameters"></a>参数

_pclsidCategory_
  
> 实时要为其设置顺序的类别类 ID。 值必须为以下值之一：
    
   - CLSID_OlkAddressBook
    
   - CLSID_OlkStore
    
_cAccts_
  
> 实时帐户数。
    
_rgAccts_
  
> 实时帐户 id 的数组。 数组的大小为_cAccts_。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_ACCT_WRONG_SORT_ORDER  <br/> |新的排序顺序与旧的排序顺序具有不同的帐户数。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
   
## <a name="remarks"></a>注解

调用方为数组指针_prgAccts_分配内存, 并为_prgAccts_点分配数组。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccountManager::GetOrder](iolkaccountmanager-getorder.md)

