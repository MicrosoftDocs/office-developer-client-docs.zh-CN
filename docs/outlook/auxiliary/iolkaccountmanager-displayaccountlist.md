---
title: IOlkAccountManagerDisplayAccountList
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a637dcab-81e0-4195-a1d5-61d9957fcf10
description: 显示的帐户设置或添加新帐户对话框。
ms.openlocfilehash: 3c7c433eb4d8f316d32b6cd12bbbbb0e1a1cee43
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774344"
---
# <a name="iolkaccountmanagerdisplayaccountlist"></a>IOlkAccountManager::DisplayAccountList

显示的**帐户设置**或**添加新帐户**对话框。 
  
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
  
> [in]向其显示的对话框是模式窗口的句柄。 可能为零。
    
_dwFlags_
  
> [in]若要修改显示的行为的标志。 
    
   - **ACCTUI_NO_WARNING**— 不显示警告更改将不会生效，直到重新启动 Outlook。 应用程序是过程与 Outlook.exe 时才适用。
    
   - **ACCTUI_SHOW_DATA_TAB**— 显示所选**数据**选项卡的**帐户设置**对话框。 未设置**ACCTUI_SHOW_ACCTWIZARD**时才有效。 
    
   - **ACCTUI_SHOW_ACCTWIZARD**— 显示**添加新帐户**对话框。 
    
_wszTitle_
  
> [in]此参数不使用，并且应为 NULL。
    
_cCategories_
  
> [in]此参数不使用，并且必须为 NULL。 
    
_rgclsidCategories_
  
> [in]此参数不使用，并且必须为 NULL。
    
_pclsidType_
  
> [in]此参数不使用，并且必须为 NULL。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |呼叫成功。  <br/> |
|E_ACCT_UI_BUSY  <br/> |无法创建对话框。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
|MAPI_E_CALL_FAILED  <br/> |**添加新帐户**对话框返回错误。  <br/> |
|MAPI_E_INVALID_PARAMETER  <br/> |_CCategories_、 _rgclsidCategories_或_pclsidType_参数为非 NULL。  <br/> |
|MAPI_E_USER_CANCEL  <br/> |**帐户设置**对话框返回错误。  <br/> |
   
## <a name="remarks"></a>说明

_CCategories_、 _rgclsidCategories_和_pclsidType_参数此时不使用，并且必须为 NULL。  _wszTitle_不使用，而且还应为 NULL。 
  

