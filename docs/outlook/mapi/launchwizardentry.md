---
title: LAUNCHWIZARDENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.LAUNCHWIZARDENTRY
api_type:
- COM
ms.assetid: 5778dffa-f01b-46b3-9c19-862793740918
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c1509918eb587c17deebf95317cf57b4ab19928a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270187"
---
# <a name="launchwizardentry"></a><span data-ttu-id="00dac-103">LAUNCHWIZARDENTRY</span><span class="sxs-lookup"><span data-stu-id="00dac-103">LAUNCHWIZARDENTRY</span></span>

  
  
<span data-ttu-id="00dac-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="00dac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="00dac-105">定义用于启动配置文件向导应用程序的函数, 以将一个或多个邮件服务添加到配置文件。</span><span class="sxs-lookup"><span data-stu-id="00dac-105">Defines a function that starts the Profile Wizard application for the purpose of adding one or more message services to a profile.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="00dac-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="00dac-106">Header file:</span></span>  <br/> |<span data-ttu-id="00dac-107">Mapiwz</span><span class="sxs-lookup"><span data-stu-id="00dac-107">Mapiwz.h</span></span>  <br/> |
|<span data-ttu-id="00dac-108">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="00dac-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="00dac-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="00dac-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="00dac-110">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="00dac-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="00dac-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="00dac-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT LAUNCHWIZARDENTRY(
  HWND hParentWnd,
  ULONG ulFlags,
  LPCSTR FAR * lppszServiceNameToAdd,
  ULONG cbBufferMax,
  LPSTR lpszNewProfileName
);
```

## <a name="parameters"></a><span data-ttu-id="00dac-112">参数</span><span class="sxs-lookup"><span data-stu-id="00dac-112">Parameters</span></span>

 <span data-ttu-id="00dac-113">_hParentWnd_</span><span class="sxs-lookup"><span data-stu-id="00dac-113">_hParentWnd_</span></span>
  
> <span data-ttu-id="00dac-114">实时呼叫者父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="00dac-114">[in] A handle to the caller's parent window.</span></span> <span data-ttu-id="00dac-115">如果调用方没有父窗口, 则_hParentWnd_参数应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="00dac-115">If the caller does not have a parent window, the  _hParentWnd_ parameter should be NULL.</span></span> 
    
 <span data-ttu-id="00dac-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="00dac-116">_ulFlags_</span></span>
  
> <span data-ttu-id="00dac-117">实时指示配置文件向导选项的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="00dac-117">[in] Bitmask of flags indicating options for the Profile Wizard.</span></span> <span data-ttu-id="00dac-118">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="00dac-118">The following flags can be set:</span></span>
    
<span data-ttu-id="00dac-119">MAPI_PW_ADD_SERVICE_ONLY</span><span class="sxs-lookup"><span data-stu-id="00dac-119">MAPI_PW_ADD_SERVICE_ONLY</span></span> 
  
> <span data-ttu-id="00dac-120">配置文件向导是仅添加通过_lppszServiceNameToAdd_参数列出的邮件服务, 而不是显示其用于选择邮件服务的页面。</span><span class="sxs-lookup"><span data-stu-id="00dac-120">The Profile Wizard is to add only the message services listed through the  _lppszServiceNameToAdd_ parameter, and not display its page for selecting message services.</span></span> 
    
<span data-ttu-id="00dac-121">MAPI_PW_FIRST_PROFILE</span><span class="sxs-lookup"><span data-stu-id="00dac-121">MAPI_PW_FIRST_PROFILE</span></span> 
  
> <span data-ttu-id="00dac-122">要创建的配置文件是此工作站的第一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="00dac-122">The profile to be created is the first one for this workstation.</span></span> 
    
<span data-ttu-id="00dac-123">MAPI_PW_HIDE_SERVICES_LIST</span><span class="sxs-lookup"><span data-stu-id="00dac-123">MAPI_PW_HIDE_SERVICES_LIST</span></span> 
  
> <span data-ttu-id="00dac-124">不应显示用于选择 "邮件服务" 的配置文件向导的页面。</span><span class="sxs-lookup"><span data-stu-id="00dac-124">The Profile Wizard's page for selecting message services should not be displayed.</span></span> 
    
<span data-ttu-id="00dac-125">MAPI_PW_LAUNCHED_BY_CONFIG</span><span class="sxs-lookup"><span data-stu-id="00dac-125">MAPI_PW_LAUNCHED_BY_CONFIG</span></span> 
  
> <span data-ttu-id="00dac-126">"配置文件向导" 由 "控制面板" 配置应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="00dac-126">The Profile Wizard was launched by the Control Panel configuration application.</span></span> 
    
<span data-ttu-id="00dac-127">MAPI_PW_PROVIDER_UI_ONLY</span><span class="sxs-lookup"><span data-stu-id="00dac-127">MAPI_PW_PROVIDER_UI_ONLY</span></span> 
  
> <span data-ttu-id="00dac-128">仅应显示服务提供商的配置对话框, 并且不应显示配置文件向导的页面。</span><span class="sxs-lookup"><span data-stu-id="00dac-128">Only the service providers's configuration dialog boxes should be displayed and the Profile Wizard's pages should not appear.</span></span> <span data-ttu-id="00dac-129">仅当设置了 MAPI_PW_ADD_SERVICE_ONLY 标志时, 才能设置此标志。</span><span class="sxs-lookup"><span data-stu-id="00dac-129">This flag can only be set if the MAPI_PW_ADD_SERVICE_ONLY flag is set.</span></span> 
    
 <span data-ttu-id="00dac-130">_lppszServiceNameToAdd_</span><span class="sxs-lookup"><span data-stu-id="00dac-130">_lppszServiceNameToAdd_</span></span>
  
> <span data-ttu-id="00dac-131">实时指向包含要添加到配置文件中的邮件服务的名称的字符串数组的指针。</span><span class="sxs-lookup"><span data-stu-id="00dac-131">[in] Pointer to an array of strings that contains the names of the message services to be added to the profile.</span></span> <span data-ttu-id="00dac-132">数组必须以 NULL 值终止。</span><span class="sxs-lookup"><span data-stu-id="00dac-132">The array must terminate with a NULL value.</span></span> 
    
 <span data-ttu-id="00dac-133">_cbBufferMax_</span><span class="sxs-lookup"><span data-stu-id="00dac-133">_cbBufferMax_</span></span>
  
> <span data-ttu-id="00dac-134">实时由_lpszNewProfileName_参数指向的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="00dac-134">[in] Size of the buffer pointed to by the  _lpszNewProfileName_ parameter.</span></span> 
    
 <span data-ttu-id="00dac-135">_lpszNewProfileName_</span><span class="sxs-lookup"><span data-stu-id="00dac-135">_lpszNewProfileName_</span></span>
  
> <span data-ttu-id="00dac-136">排除指向基于**LAUNCHWIZARDENTRY**的函数的字符串缓冲区的指针返回所创建的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="00dac-136">[out] Pointer to a string buffer where the function based on **LAUNCHWIZARDENTRY** returns the name of the created profile.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="00dac-137">返回值</span><span class="sxs-lookup"><span data-stu-id="00dac-137">Return value</span></span>

<span data-ttu-id="00dac-138">S_OK</span><span class="sxs-lookup"><span data-stu-id="00dac-138">S_OK</span></span> 
  
> <span data-ttu-id="00dac-139">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="00dac-139">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="00dac-140">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="00dac-140">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="00dac-141">意外或未知来源的错误阻止操作完成。</span><span class="sxs-lookup"><span data-stu-id="00dac-141">An error of unexpected or unknown origin prevented the operation from completing.</span></span> <span data-ttu-id="00dac-142">可能的原因包括初始化配置文件向导的 MAPI 子系统失败、无法访问默认配置文件以及从对话框返回错误。</span><span class="sxs-lookup"><span data-stu-id="00dac-142">Possibilities include failure to initialize the MAPI subsystem for the Profile Wizard, inability to access the default profile, and an error return from the dialog box.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="00dac-143">注解</span><span class="sxs-lookup"><span data-stu-id="00dac-143">Remarks</span></span>

<span data-ttu-id="00dac-144">**LAUNCHWIZARDENTRY**函数原型的 MAPI 实现是 mapi 配置文件向导应用程序的入口点。</span><span class="sxs-lookup"><span data-stu-id="00dac-144">The MAPI implementation of the **LAUNCHWIZARDENTRY** function prototype is the entry point into the MAPI Profile Wizard application.</span></span> <span data-ttu-id="00dac-145">MAPI 将此入口点命名为**LaunchWizard**。</span><span class="sxs-lookup"><span data-stu-id="00dac-145">MAPI names this entry point **LaunchWizard**.</span></span> 
  
<span data-ttu-id="00dac-146">在_ulFlags_参数中设置 MAPI_PW_ADD_SERVICE_ONLY 标志时, 将应用以下规则:</span><span class="sxs-lookup"><span data-stu-id="00dac-146">When the MAPI_PW_ADD_SERVICE_ONLY flag is set in the  _ulFlags_ parameter, the following rules apply:</span></span> 
  
- <span data-ttu-id="00dac-147">MAPI_PW_LAUNCHED_BY_CONFIG 标志禁止显示欢迎页面。</span><span class="sxs-lookup"><span data-stu-id="00dac-147">The MAPI_PW_LAUNCHED_BY_CONFIG flag inhibits the welcome page from being displayed.</span></span> 
    
- <span data-ttu-id="00dac-148">仅当没有默认配置文件时, MAPI_PW_HIDE_SERVICES_LIST 和 MAPI_PW_PROVIDER_UI_ONLY 标志才有用。</span><span class="sxs-lookup"><span data-stu-id="00dac-148">The MAPI_PW_HIDE_SERVICES_LIST and MAPI_PW_PROVIDER_UI_ONLY flags are useful only when there is no default profile.</span></span> <span data-ttu-id="00dac-149">在这种情况下, 这些标志决定要显示哪个配置文件向导页。</span><span class="sxs-lookup"><span data-stu-id="00dac-149">In this case these flags determine which Profile Wizard page is to be displayed.</span></span> 
    
- <span data-ttu-id="00dac-150">如果存在默认配置文件, 则不会显示任何配置文件向导页。</span><span class="sxs-lookup"><span data-stu-id="00dac-150">If a default profile exists, none of the Profile Wizard pages are to be displayed.</span></span> 
    
- <span data-ttu-id="00dac-151">如果存在默认配置文件, 则仅通过_lppszServiceNameToAdd_参数列出了一个邮件服务, 并且该邮件服务已在默认配置文件中, 配置文件向导返回 S_OK, 而不向配置文件添加任何内容。</span><span class="sxs-lookup"><span data-stu-id="00dac-151">If a default profile exists, only one message service is listed through the  _lppszServiceNameToAdd_ parameter, and that message service is already in the default profile, the Profile Wizard returns S_OK without adding anything to the profile.</span></span> 
    
<span data-ttu-id="00dac-152">对于要添加到配置文件中的每个邮件服务, 配置文件向导将根据[MSGSERVICEENTRY](msgserviceentry.md)原型调用服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="00dac-152">For every message service to be added to the profile, the Profile Wizard calls the service's entry point function based on the [MSGSERVICEENTRY](msgserviceentry.md) prototype.</span></span> <span data-ttu-id="00dac-153">对于从要添加到配置文件中的邮件服务中选择的每个服务提供程序, "配置文件向导" 将根据[WIZARDENTRY](wizardentry.md)原型调用提供程序的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="00dac-153">For each service provider selected from a message service to be added to the profile, the Profile Wizard calls the provider's entry point function based on the [WIZARDENTRY](wizardentry.md) prototype.</span></span> <span data-ttu-id="00dac-154">在交互式配置过程中, 属性页中的每个用户事件都会使配置文件向导根据[SERVICEWIZARDDLGPROC](servicewizarddlgproc.md)原型调用提供程序的回调函数。</span><span class="sxs-lookup"><span data-stu-id="00dac-154">During interactive configuration, every user event in the property pages causes the Profile Wizard to call the provider's callback function based on the [SERVICEWIZARDDLGPROC](servicewizarddlgproc.md) prototype.</span></span> 
  
<span data-ttu-id="00dac-155">如果要添加到配置文件中的服务提供程序支持配置文件向导页, 则它必须允许配置文件的编程配置。</span><span class="sxs-lookup"><span data-stu-id="00dac-155">If a service provider being added to the profile supports the Profile Wizard pages, it must allow programmatic configuration of the profile.</span></span>
  

