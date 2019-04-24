---
title: ISocialProviderGetSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 371b48c5-6d77-4d2d-890c-bb234c7eaabc
description: 获取 ISocialSession 接口。
ms.openlocfilehash: afa13bddd5cbbc53081f6ae7ddcc1671d1c40303
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285770"
---
# <a name="isocialprovidergetsession"></a>ISocialProvider::GetSession

获取[ISocialSession](isocialsessioniunknown.md)接口。 
  
```cpp
HRESULT _stdcall GetSession([out, retval] ISocialSession** session);
```

## <a name="parameters"></a>参数

_Session_
  
> [out] **ISocialSession** 界面。 
    
## <a name="remarks"></a>说明

Outlook Social Connector (.osc) 使用**ISocialSession**接口登录到社交网络。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

