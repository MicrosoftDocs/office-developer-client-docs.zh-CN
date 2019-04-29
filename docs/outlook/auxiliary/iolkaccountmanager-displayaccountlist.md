---
title: IOlkAccountManagerDisplayAccountList
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a637dcab-81e0-4195-a1d5-61d9957fcf10
description: 显示 "帐户设置" 或 "添加新帐户" 对话框。
ms.openlocfilehash: ecf5242fa4f224516e12e667ab66fd0adfe4a25d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415031"
---
# <a name="iolkaccountmanagerdisplayaccountlist"></a>IOlkAccountManager::DisplayAccountList

显示 "**帐户设置**" 或 "**添加新帐户**" 对话框。 
  
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
  
> 实时显示的对话框为其模式的窗口的句柄。 可能为零。
    
_dwFlags_
  
> 实时用于修改显示器行为的标志。 
    
   - **ACCTUI_NO_WARNING**—不显示警告, 在重新启动 Outlook 之前, 更改不会生效。 仅当应用程序使用 Outlook 在进程中运行时适用。
    
   - **ACCTUI_SHOW_DATA_TAB**—显示选中 "**数据**" 选项卡的 "**帐户设置**" 对话框。 仅在未设置**ACCTUI_SHOW_ACCTWIZARD**时有效。 
    
   - **ACCTUI_SHOW_ACCTWIZARD**—显示 "**添加新帐户**" 对话框。 
    
_wszTitle_
  
> 实时不使用此参数, 应为 NULL。
    
_cCategories_
  
> 实时不使用此参数, 必须为 NULL。 
    
_rgclsidCategories_
  
> 实时不使用此参数, 必须为 NULL。
    
_pclsidType_
  
> 实时不使用此参数, 必须为 NULL。
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|E_ACCT_UI_BUSY  <br/> |无法创建对话框。  <br/> |
|E_OLK_NOT_INITIALIZED  <br/> |帐户管理器已初始化，不能使用。  <br/> |
|MAPI_E_CALL_FAILED  <br/> |"**添加新帐户**" 对话框返回一个错误。  <br/> |
|MAPI_E_INVALID_PARAMETER  <br/> |_cCategories_、 _rgclsidCategories_或_pclsidType_参数为非 NULL。  <br/> |
|MAPI_E_USER_CANCEL  <br/> |"**帐户设置**" 对话框返回一个错误。  <br/> |
   
## <a name="remarks"></a>说明

_cCategories_、 _rgclsidCategories_和_pclsidType_参数目前不使用, 并且必须为 NULL。  _wszTitle_不使用, 也应为 NULL。 
  

