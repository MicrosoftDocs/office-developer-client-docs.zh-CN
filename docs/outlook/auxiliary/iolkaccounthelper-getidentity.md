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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400136"
---
# <a name="iolkaccounthelpergetidentity"></a>IOlkAccountHelper::GetIdentity

获取帐户的配置文件名称。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkAccountHelper](iolkaccounthelper.md)。
  
```cpp
HRESULT IOlkAccountHelper::GetIdentity (  
    LPWSTR pwszIdentity, 
    DWORD *pcch 
);
```

## <a name="parameters"></a>参数

_pwszIdentity_
  
> [in][输出]配置文件的名称。
    
_pcch_
  
> [in][输出]时调用此方法，都包含_pwszIdentity_已分配的大小 （以字符数）。 返回时，包含的实际长度，包括 0 终止，返回的配置文件名称字符。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_OUTOFMEMORY  <br/> |返回的配置文件名称的长度超过_pwszIdentity_的大小。  <br/> |
|E_INVALIDARG  <br/> | _pcch_为 NULL。  <br/> |
   
## <a name="remarks"></a>说明

如果_pwszIdentity_太小，若要保留的配置文件名称，将不会设置返回时，并且_pcch_将指向_pwszIdentity_所需的大小。
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)
- [PidTagProfileName](https://msdn.microsoft.com/library/13ca726d-ae7a-4da9-9c8e-3db3c479f839%28Office.15%29.aspx)

