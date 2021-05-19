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
# <a name="iolkaccountmanagerdisplayaccountlist"></a><span data-ttu-id="bce07-103">IOlkAccountManager::DisplayAccountList</span><span class="sxs-lookup"><span data-stu-id="bce07-103">IOlkAccountManager::DisplayAccountList</span></span>

<span data-ttu-id="bce07-104">Displays either the **Account 设置** or Add **New Account** dialog box.</span><span class="sxs-lookup"><span data-stu-id="bce07-104">Displays either the **Account Settings** or **Add New Account** dialog box.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="bce07-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="bce07-105">Quick info</span></span>

<span data-ttu-id="bce07-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="bce07-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="bce07-107">参数</span><span class="sxs-lookup"><span data-stu-id="bce07-107">Parameters</span></span>

<span data-ttu-id="bce07-108">_hwnd_</span><span class="sxs-lookup"><span data-stu-id="bce07-108">_hwnd_</span></span>
  
> <span data-ttu-id="bce07-109">[in]所显示对话框已模式化的窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="bce07-109">[in] The handle to the window to which the displayed dialog box is modal.</span></span> <span data-ttu-id="bce07-110">可能为零。</span><span class="sxs-lookup"><span data-stu-id="bce07-110">May be zero.</span></span>
    
<span data-ttu-id="bce07-111">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="bce07-111">_dwFlags_</span></span>
  
> <span data-ttu-id="bce07-112">[in]用于修改显示行为的标志。</span><span class="sxs-lookup"><span data-stu-id="bce07-112">[in] Flags to modify the behavior of the display.</span></span> 
    
   - <span data-ttu-id="bce07-113">**ACCTUI_NO_WARNING**- 在重新启动更改之前，不要显示Outlook警告。</span><span class="sxs-lookup"><span data-stu-id="bce07-113">**ACCTUI_NO_WARNING**—Do not display the warning that changes will not take effect until Outlook is restarted.</span></span> <span data-ttu-id="bce07-114">仅在应用程序在进程内运行并运行 Outlook.exe。</span><span class="sxs-lookup"><span data-stu-id="bce07-114">Applies only if the application is running in-process with Outlook.exe.</span></span>
    
   - <span data-ttu-id="bce07-115">**ACCTUI_SHOW_DATA_TAB** 显示 **"帐户设置"** 对话框，并选中 **"数据"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bce07-115">**ACCTUI_SHOW_DATA_TAB**—Show the **Account Settings** dialog box with the **Data** tab selected.</span></span> <span data-ttu-id="bce07-116">仅在未设置 **ACCTUI_SHOW_ACCTWIZARD** 时有效。</span><span class="sxs-lookup"><span data-stu-id="bce07-116">Valid only if **ACCTUI_SHOW_ACCTWIZARD** is not set.</span></span> 
    
   - <span data-ttu-id="bce07-117">**ACCTUI_SHOW_ACCTWIZARD** 显示" **添加新帐户"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="bce07-117">**ACCTUI_SHOW_ACCTWIZARD**—Display the **Add New Account** dialog box.</span></span> 
    
<span data-ttu-id="bce07-118">_wszTitle_</span><span class="sxs-lookup"><span data-stu-id="bce07-118">_wszTitle_</span></span>
  
> <span data-ttu-id="bce07-119">[in]此参数未使用，并且应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="bce07-119">[in] This parameter is not used and should be NULL.</span></span>
    
<span data-ttu-id="bce07-120">_cCategories_</span><span class="sxs-lookup"><span data-stu-id="bce07-120">_cCategories_</span></span>
  
> <span data-ttu-id="bce07-121">[in]此参数未使用，并且必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="bce07-121">[in] This parameter is not used and must be NULL.</span></span> 
    
<span data-ttu-id="bce07-122">_rgclsidCategories_</span><span class="sxs-lookup"><span data-stu-id="bce07-122">_rgclsidCategories_</span></span>
  
> <span data-ttu-id="bce07-123">[in]此参数未使用，并且必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="bce07-123">[in] This parameter is not used and must be NULL.</span></span>
    
<span data-ttu-id="bce07-124">_pclsidType_</span><span class="sxs-lookup"><span data-stu-id="bce07-124">_pclsidType_</span></span>
  
> <span data-ttu-id="bce07-125">[in]此参数未使用，并且必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="bce07-125">[in] This parameter is not used and must be NULL.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="bce07-126">返回值</span><span class="sxs-lookup"><span data-stu-id="bce07-126">Return values</span></span>

|<span data-ttu-id="bce07-127">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="bce07-127">**HRESULT**</span></span>|<span data-ttu-id="bce07-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="bce07-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bce07-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="bce07-129">S_OK</span></span>  <br/> |<span data-ttu-id="bce07-130">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="bce07-130">The call was successful.</span></span>  <br/> |
|<span data-ttu-id="bce07-131">E_ACCT_UI_BUSY</span><span class="sxs-lookup"><span data-stu-id="bce07-131">E_ACCT_UI_BUSY</span></span>  <br/> |<span data-ttu-id="bce07-132">无法创建对话框。</span><span class="sxs-lookup"><span data-stu-id="bce07-132">The dialog box could not be created.</span></span>  <br/> |
|<span data-ttu-id="bce07-133">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="bce07-133">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="bce07-134">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="bce07-134">The account manager has not been initialized for use.</span></span>  <br/> |
|<span data-ttu-id="bce07-135">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="bce07-135">MAPI_E_CALL_FAILED</span></span>  <br/> |<span data-ttu-id="bce07-136">" **添加新帐户"** 对话框返回错误。</span><span class="sxs-lookup"><span data-stu-id="bce07-136">The **Add New Account** dialog box returned an error.</span></span>  <br/> |
|<span data-ttu-id="bce07-137">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="bce07-137">MAPI_E_INVALID_PARAMETER</span></span>  <br/> |<span data-ttu-id="bce07-138">_cCategories_ _、rgclsidCategories_ 或 _pclsidType_ 参数为非 NULL。</span><span class="sxs-lookup"><span data-stu-id="bce07-138">The  _cCategories_,  _rgclsidCategories_, or  _pclsidType_ parameter is non-NULL.</span></span>  <br/> |
|<span data-ttu-id="bce07-139">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="bce07-139">MAPI_E_USER_CANCEL</span></span>  <br/> |<span data-ttu-id="bce07-140">The **Account 设置** dialog box returned an error.</span><span class="sxs-lookup"><span data-stu-id="bce07-140">The **Account Settings** dialog box returned an error.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bce07-141">备注</span><span class="sxs-lookup"><span data-stu-id="bce07-141">Remarks</span></span>

<span data-ttu-id="bce07-142">此时不会使用 cCategories、rgclsidCategories 和 _pclsidType_ 参数，并且必须为 NULL。  </span><span class="sxs-lookup"><span data-stu-id="bce07-142">The  _cCategories_,  _rgclsidCategories_, and  _pclsidType_ parameters are not used at this time and must be NULL.</span></span>  <span data-ttu-id="bce07-143">_不使用 wszTitle，_ 并且也应该为 NULL。</span><span class="sxs-lookup"><span data-stu-id="bce07-143">_wszTitle_ is not used and should also be NULL.</span></span> 
  

