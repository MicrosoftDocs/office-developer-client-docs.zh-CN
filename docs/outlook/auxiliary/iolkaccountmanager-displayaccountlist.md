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
# <a name="iolkaccountmanagerdisplayaccountlist"></a><span data-ttu-id="a6d66-103">IOlkAccountManager::DisplayAccountList</span><span class="sxs-lookup"><span data-stu-id="a6d66-103">IOlkAccountManager::DisplayAccountList</span></span>

<span data-ttu-id="a6d66-104">显示的**帐户设置**或**添加新帐户**对话框。</span><span class="sxs-lookup"><span data-stu-id="a6d66-104">Displays either the **Account Settings** or **Add New Account** dialog box.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="a6d66-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="a6d66-105">Quick info</span></span>

<span data-ttu-id="a6d66-106">See [IOlkAccountManager](iolkaccountmanager.md).</span><span class="sxs-lookup"><span data-stu-id="a6d66-106">See [IOlkAccountManager](iolkaccountmanager.md).</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="a6d66-107">参数</span><span class="sxs-lookup"><span data-stu-id="a6d66-107">Parameters</span></span>

<span data-ttu-id="a6d66-108">_hwnd_</span><span class="sxs-lookup"><span data-stu-id="a6d66-108">_hwnd_</span></span>
  
> <span data-ttu-id="a6d66-109">[in]向其显示的对话框是模式窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="a6d66-109">[in] The handle to the window to which the displayed dialog box is modal.</span></span> <span data-ttu-id="a6d66-110">可能为零。</span><span class="sxs-lookup"><span data-stu-id="a6d66-110">May be zero.</span></span>
    
<span data-ttu-id="a6d66-111">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="a6d66-111">_dwFlags_</span></span>
  
> <span data-ttu-id="a6d66-112">[in]若要修改显示的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="a6d66-112">[in] Flags to modify the behavior of the display.</span></span> 
    
   - <span data-ttu-id="a6d66-113">**ACCTUI_NO_WARNING**— 不显示警告更改将不会生效，直到重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="a6d66-113">**ACCTUI_NO_WARNING**—Do not display the warning that changes will not take effect until Outlook is restarted.</span></span> <span data-ttu-id="a6d66-114">应用程序是过程与 Outlook.exe 时才适用。</span><span class="sxs-lookup"><span data-stu-id="a6d66-114">Applies only if the application is running in-process with Outlook.exe.</span></span>
    
   - <span data-ttu-id="a6d66-115">**ACCTUI_SHOW_DATA_TAB**— 显示所选**数据**选项卡的**帐户设置**对话框。</span><span class="sxs-lookup"><span data-stu-id="a6d66-115">**ACCTUI_SHOW_DATA_TAB**—Show the **Account Settings** dialog box with the **Data** tab selected.</span></span> <span data-ttu-id="a6d66-116">未设置**ACCTUI_SHOW_ACCTWIZARD**时才有效。</span><span class="sxs-lookup"><span data-stu-id="a6d66-116">Valid only if **ACCTUI_SHOW_ACCTWIZARD** is not set.</span></span> 
    
   - <span data-ttu-id="a6d66-117">**ACCTUI_SHOW_ACCTWIZARD**— 显示**添加新帐户**对话框。</span><span class="sxs-lookup"><span data-stu-id="a6d66-117">**ACCTUI_SHOW_ACCTWIZARD**—Display the **Add New Account** dialog box.</span></span> 
    
<span data-ttu-id="a6d66-118">_wszTitle_</span><span class="sxs-lookup"><span data-stu-id="a6d66-118">_wszTitle_</span></span>
  
> <span data-ttu-id="a6d66-119">[in]此参数不使用，并且应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a6d66-119">[in] This parameter is not used and should be NULL.</span></span>
    
<span data-ttu-id="a6d66-120">_cCategories_</span><span class="sxs-lookup"><span data-stu-id="a6d66-120">_cCategories_</span></span>
  
> <span data-ttu-id="a6d66-121">[in]此参数不使用，并且必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a6d66-121">[in] This parameter is not used and must be NULL.</span></span> 
    
<span data-ttu-id="a6d66-122">_rgclsidCategories_</span><span class="sxs-lookup"><span data-stu-id="a6d66-122">_rgclsidCategories_</span></span>
  
> <span data-ttu-id="a6d66-123">[in]此参数不使用，并且必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a6d66-123">[in] This parameter is not used and must be NULL.</span></span>
    
<span data-ttu-id="a6d66-124">_pclsidType_</span><span class="sxs-lookup"><span data-stu-id="a6d66-124">_pclsidType_</span></span>
  
> <span data-ttu-id="a6d66-125">[in]此参数不使用，并且必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a6d66-125">[in] This parameter is not used and must be NULL.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="a6d66-126">返回值</span><span class="sxs-lookup"><span data-stu-id="a6d66-126">Return values</span></span>

|<span data-ttu-id="a6d66-127">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="a6d66-127">**HRESULT**</span></span>|<span data-ttu-id="a6d66-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="a6d66-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a6d66-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6d66-129">S_OK</span></span>  <br/> |<span data-ttu-id="a6d66-130">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="a6d66-130">The call was successful.</span></span>  <br/> |
|<span data-ttu-id="a6d66-131">E_ACCT_UI_BUSY</span><span class="sxs-lookup"><span data-stu-id="a6d66-131">E_ACCT_UI_BUSY</span></span>  <br/> |<span data-ttu-id="a6d66-132">无法创建对话框。</span><span class="sxs-lookup"><span data-stu-id="a6d66-132">The dialog box could not be created.</span></span>  <br/> |
|<span data-ttu-id="a6d66-133">E_OLK_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="a6d66-133">E_OLK_NOT_INITIALIZED</span></span>  <br/> |<span data-ttu-id="a6d66-134">帐户管理器已初始化，不能使用。</span><span class="sxs-lookup"><span data-stu-id="a6d66-134">The account manager has not been initialized for use.</span></span>  <br/> |
|<span data-ttu-id="a6d66-135">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="a6d66-135">MAPI_E_CALL_FAILED</span></span>  <br/> |<span data-ttu-id="a6d66-136">**添加新帐户**对话框返回错误。</span><span class="sxs-lookup"><span data-stu-id="a6d66-136">The **Add New Account** dialog box returned an error.</span></span>  <br/> |
|<span data-ttu-id="a6d66-137">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="a6d66-137">MAPI_E_INVALID_PARAMETER</span></span>  <br/> |<span data-ttu-id="a6d66-138">_CCategories_、 _rgclsidCategories_或_pclsidType_参数为非 NULL。</span><span class="sxs-lookup"><span data-stu-id="a6d66-138">The  _cCategories_,  _rgclsidCategories_, or  _pclsidType_ parameter is non-NULL.</span></span>  <br/> |
|<span data-ttu-id="a6d66-139">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="a6d66-139">MAPI_E_USER_CANCEL</span></span>  <br/> |<span data-ttu-id="a6d66-140">**帐户设置**对话框返回错误。</span><span class="sxs-lookup"><span data-stu-id="a6d66-140">The **Account Settings** dialog box returned an error.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a6d66-141">说明</span><span class="sxs-lookup"><span data-stu-id="a6d66-141">Remarks</span></span>

<span data-ttu-id="a6d66-142">_CCategories_、 _rgclsidCategories_和_pclsidType_参数此时不使用，并且必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a6d66-142">The  _cCategories_,  _rgclsidCategories_, and  _pclsidType_ parameters are not used at this time and must be NULL.</span></span>  <span data-ttu-id="a6d66-143">_wszTitle_不使用，而且还应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a6d66-143">_wszTitle_ is not used and should also be NULL.</span></span> 
  

