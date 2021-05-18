---
title: IOlkAccountManagerInit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0e5ffb61-1469-bc91-f237-27d1156179cd
description: 初始化帐户管理器以使用。
ms.openlocfilehash: 5a643a4636251afc98750be8acf47cd3bdab3847
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322034"
---
# <a name="iolkaccountmanagerinit"></a>IOlkAccountManager::Init

初始化帐户管理器以使用。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccountManager](iolkaccountmanager.md).
  
```cpp
HRESULT IOlkAccountManager::Init (  
    IOlkAccountHelper *pAcctHelper, 
    DWORD dwFlags 
);

```

## <a name="parameters"></a>参数

_pAcctHelper_
  
> [in]提供 [帐户帮助程序功能的 IOlkAccountHelper](iolkaccounthelper.md) 接口。 
    
_dwFlags_
  
> [] in若要修改行为的标志。
    
   - **ACCT_INIT_NO_STORES_CHECK** — 阻止 (IMAP 帐户等) 与关联存储同步。 
    
   - **ACCT_INIT_NOSYNCH_MAPI_ACCTS** - 阻止 MAPI 服务与帐户同步。 
   
   - **ACCT_INIT_NO_NOTIFICATIONS** — 阻止帐户管理器截获用于其他应用程序的广播消息。 
   
   - **OLK_ACCOUNT_NO_FLAGS** - 将 MAPI 服务与帐户同步。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_OLK_ALREADY_INITIALIZED  <br/> |**已调用 Init。**  <br/> |
|E_OLK_REGISTRY  <br/> |帐户管理员无法访问所需的注册表设置。  <br/> |
   
## <a name="remarks"></a>备注

客户端必须先调用 **IOlkAccountManager：：Init** 以初始化帐户管理器，然后才能使用帐户管理器访问帐户或设置通知。 由于Outlook时会自动将 MAPI 服务与帐户同步，ACCT_INIT_NOSYNCH_MAPI_ACCTS，除非有特定原因需要同步。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)

