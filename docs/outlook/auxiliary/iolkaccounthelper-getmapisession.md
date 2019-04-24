---
title: IOlkAccountHelperGetMapiSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a431787c-6e9a-9be1-165f-98c778d12e3e
description: 打开 MAPI 会话并维护对帐户管理员会话的引用。
ms.openlocfilehash: 5886ac1ae1bb8f3b43e09f49e48434d9a73656ce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322174"
---
# <a name="iolkaccounthelpergetmapisession"></a>IOlkAccountHelper::GetMapiSession

打开 MAPI 会话并维护对帐户管理员会话的引用。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkAccountHelper](iolkaccounthelper.md)。
  
```cpp
HRESULT IOlkAccountHelper::GetMapiSession(  
    LPUNKNOWN *ppmsess 
);
```

## <a name="parameters"></a>参数

_ppmsess_
  
> 排除当前的 MAPI 会话。
    
## <a name="return-values"></a>返回值

如果该调用成功，则返回 S_OK否则为一个错误代码。
  
## <a name="remarks"></a>注解

由于存在循环引用问题, 帐户管理员本身无法维护对 MAPI 会话的引用。
  
## <a name="see-also"></a>另请参阅

- [IOlkAccountHelper::HandsOffSession](iolkaccounthelper-handsoffsession.md)
- [IMAPISession : IUnknown](https://msdn.microsoft.com/library/5650fa2a-6e62-451c-964e-363f7bee2344%28Office.15%29.aspx)

