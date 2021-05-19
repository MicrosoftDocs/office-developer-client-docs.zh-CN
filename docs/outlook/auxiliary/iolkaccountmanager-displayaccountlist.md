---
title: IOlkAccountManagerDisplayAccountList
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a637dcab-81e0-4195-a1d5-61d9957fcf10
description: Displays either the Account 设置 or Add New Account dialog box.
ms.openlocfilehash: ecf5242fa4f224516e12e667ab66fd0adfe4a25d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415031"
---
# <a name="iolkaccountmanagerdisplayaccountlist"></a>IOlkAccountManager::DisplayAccountList

Displays either the **Account 设置** or Add **New Account** dialog box. 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccountManager](iolkaccountmanager.md).
  
```cpp
HRESULT IOlkAccountManager::DisplayAccountList ( 
    HWND hwnd,
    DWORD dwFlags,
    LPCWSTR wszTitle,
    DWORD cCategories,
    const CLSID * rgclsidCategories,
    const CLSID * pclsidType
);

```

## <a name="parameters"></a>参数

_hwnd_
  
> [in]所显示对话框已模式化的窗口的句柄。 可能为零。
    
_dwFlags_
  
> [in]用于修改显示行为的标志。 
    
   - **ACCTUI_NO_WARNING**- 在重新启动更改之前，不要显示Outlook警告。 仅在应用程序在进程内运行并运行 Outlook.exe。
    
   - **ACCTUI_SHOW_DATA_TAB** 显示 **"帐户设置"** 对话框，并选中 **"数据"** 选项卡。 仅在未设置 **ACCTUI_SHOW_ACCTWIZARD** 时有效。 
    
   - **ACCTUI_SHOW_ACCTWIZARD** 显示" **添加新帐户"** 对话框。 
    
_wszTitle_
  
> [in]此参数未使用，并且应为 NULL。
    
_cCategories_
  
> [in]此参数未使用，并且必须为 NULL。 
    
_rgclsidCategories_
  
> [in]此参数未使用，并且必须为 NULL。
    
_pclsidType_
  
> [in]此参数未使用，并且必须为 NULL。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |呼叫成功。  <br/> |
|E_ACCT_UI_BUSY  <br/> |无法创建对话框。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
|MAPI_E_CALL_FAILED  <br/> |" **添加新帐户"** 对话框返回错误。  <br/> |
|MAPI_E_INVALID_PARAMETER  <br/> |_cCategories_ _、rgclsidCategories_ 或 _pclsidType_ 参数为非 NULL。  <br/> |
|MAPI_E_USER_CANCEL  <br/> |The **Account 设置** dialog box returned an error.  <br/> |
   
## <a name="remarks"></a>备注

此时不会使用 cCategories、rgclsidCategories 和 _pclsidType_ 参数，并且必须为 NULL。    _不使用 wszTitle，_ 并且也应该为 NULL。 
  

