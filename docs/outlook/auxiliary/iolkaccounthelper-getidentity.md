---
title: IOlkAccountHelperGetIdentity
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea8b8f02-959f-cd71-9cfe-5ebdf4bae2bc
description: 获取帐户的配置文件名称。
ms.openlocfilehash: d725f309a29b026395e2795a49d31b45a4a49562
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322104"
---
# <a name="iolkaccounthelpergetidentity"></a>IOlkAccountHelper::GetIdentity

获取帐户的配置文件名称。
  
## <a name="quick-info"></a>快速信息

请参阅 [IOlkAccountHelper](iolkaccounthelper.md)。
  
```cpp
HRESULT IOlkAccountHelper::GetIdentity (  
    LPWSTR pwszIdentity, 
    DWORD *pcch 
);
```

## <a name="parameters"></a>参数

_pwszIdentity_
  
> [in][out]配置文件名称。
    
_pcch_
  
> [in][out]调用此方法时，包含 ( _pwszIdentity_) 字符数的大小。 返回时，包含返回的配置文件名称的实际长度，包括以 0 为终止符的字符。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_OUTOFMEMORY  <br/> |返回的配置文件名称长于  _pwszIdentity 的大小_。  <br/> |
|E_INVALIDARG  <br/> | _pcch_ 为 NULL。  <br/> |
   
## <a name="remarks"></a>备注

如果  _pwszIdentity_ 太小，无法保留配置文件名称，则返回时不会设置该名称  _，pcch_ 将指向  _pwszIdentity 所需的大小_。
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)
- [PidTagProfileName](https://msdn.microsoft.com/library/13ca726d-ae7a-4da9-9c8e-3db3c479f839%28Office.15%29.aspx)

