---
title: IOlkAccountManagerInit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0e5ffb61-1469-bc91-f237-27d1156179cd
description: 初始化的程序使用的帐户管理器。
ms.openlocfilehash: 621c6a73ab2bcbdff17b87ce15af8b4e0c2e1e24
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774335"
---
# <a name="iolkaccountmanagerinit"></a>IOlkAccountManager::Init

初始化的程序使用的帐户管理器。
  
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
  
> [in][IOlkAccountHelper](iolkaccounthelper.md)接口提供帐户帮助程序功能。 
    
_dwFlags_
  
> [] in若要修改行为的标志。
    
   - **ACCT_INIT_NO_STORES_CHECK** — 防止与相关联的存储进行同步的帐户 （例如 IMAP 帐户）。 
    
   - **ACCT_INIT_NOSYNCH_MAPI_ACCTS** — 阻止 MAPI 服务帐户与同步。 
    
   - **OLK_ACCOUNT_NO_FLAGS** — 同步 MAPI 服务帐户。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_OLK_ALREADY_INITIALIZED  <br/> |已调用**Init** 。  <br/> |
|E_OLK_REGISTRY  <br/> |帐户管理器无法访问所需的注册表设置。  <br/> |
   
## <a name="remarks"></a>说明

客户端之前必须调用**IOlkAccountManager::Init**初始化帐户管理器使用的帐户管理器可以访问帐户或设置通知。 由于 Outlook 自动同步 MAPI 服务在启动时的帐户，使用**ACCT_INIT_NOSYNCH_MAPI_ACCTS** ，除非有具体原因同步。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)

