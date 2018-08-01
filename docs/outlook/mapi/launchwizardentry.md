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
ms.openlocfilehash: d80671331c2760c574ab32d79115a352ee4bcf25
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776157"
---
# <a name="launchwizardentry"></a><span data-ttu-id="0bed2-103">LAUNCHWIZARDENTRY</span><span class="sxs-lookup"><span data-stu-id="0bed2-103">LAUNCHWIZARDENTRY</span></span>

  
  
<span data-ttu-id="0bed2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0bed2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0bed2-105">定义启动配置文件向导应用程序以便向一个配置文件中添加一个或多个消息服务的函数。</span><span class="sxs-lookup"><span data-stu-id="0bed2-105">Defines a function that starts the Profile Wizard application for the purpose of adding one or more message services to a profile.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0bed2-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="0bed2-106">Header file:</span></span>  <br/> |<span data-ttu-id="0bed2-107">Mapiwz.h</span><span class="sxs-lookup"><span data-stu-id="0bed2-107">Mapiwz.h</span></span>  <br/> |
|<span data-ttu-id="0bed2-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="0bed2-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="0bed2-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="0bed2-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="0bed2-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="0bed2-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="0bed2-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="0bed2-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT LAUNCHWIZARDENTRY(
  HWND hParentWnd,
  ULONG ulFlags,
  LPCSTR FAR * lppszServiceNameToAdd,
  ULONG cbBufferMax,
  LPSTR lpszNewProfileName
);
```

## <a name="parameters"></a><span data-ttu-id="0bed2-112">参数</span><span class="sxs-lookup"><span data-stu-id="0bed2-112">Parameters</span></span>

 <span data-ttu-id="0bed2-113">_hParentWnd_</span><span class="sxs-lookup"><span data-stu-id="0bed2-113">_hParentWnd_</span></span>
  
> <span data-ttu-id="0bed2-114">[in]呼叫者的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="0bed2-114">[in] A handle to the caller's parent window.</span></span> <span data-ttu-id="0bed2-115">如果呼叫者没有父窗口， _hParentWnd_参数应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0bed2-115">If the caller does not have a parent window, the  _hParentWnd_ parameter should be NULL.</span></span> 
    
 <span data-ttu-id="0bed2-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0bed2-116">_ulFlags_</span></span>
  
> <span data-ttu-id="0bed2-117">[in]指示用于配置文件向导选项标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="0bed2-117">[in] Bitmask of flags indicating options for the Profile Wizard.</span></span> <span data-ttu-id="0bed2-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="0bed2-118">The following flags can be set:</span></span>
    
<span data-ttu-id="0bed2-119">MAPI_PW_ADD_SERVICE_ONLY</span><span class="sxs-lookup"><span data-stu-id="0bed2-119">MAPI_PW_ADD_SERVICE_ONLY</span></span> 
  
> <span data-ttu-id="0bed2-120">配置文件向导是添加了通过_lppszServiceNameToAdd_参数列出这些消息服务并不显示其页面，以便选择消息服务。</span><span class="sxs-lookup"><span data-stu-id="0bed2-120">The Profile Wizard is to add only the message services listed through the  _lppszServiceNameToAdd_ parameter, and not display its page for selecting message services.</span></span> 
    
<span data-ttu-id="0bed2-121">MAPI_PW_FIRST_PROFILE</span><span class="sxs-lookup"><span data-stu-id="0bed2-121">MAPI_PW_FIRST_PROFILE</span></span> 
  
> <span data-ttu-id="0bed2-122">要创建的配置文件是为此工作站的第一个。</span><span class="sxs-lookup"><span data-stu-id="0bed2-122">The profile to be created is the first one for this workstation.</span></span> 
    
<span data-ttu-id="0bed2-123">MAPI_PW_HIDE_SERVICES_LIST</span><span class="sxs-lookup"><span data-stu-id="0bed2-123">MAPI_PW_HIDE_SERVICES_LIST</span></span> 
  
> <span data-ttu-id="0bed2-124">不应显示用于选择消息服务的配置文件向导的页。</span><span class="sxs-lookup"><span data-stu-id="0bed2-124">The Profile Wizard's page for selecting message services should not be displayed.</span></span> 
    
<span data-ttu-id="0bed2-125">MAPI_PW_LAUNCHED_BY_CONFIG</span><span class="sxs-lookup"><span data-stu-id="0bed2-125">MAPI_PW_LAUNCHED_BY_CONFIG</span></span> 
  
> <span data-ttu-id="0bed2-126">配置文件向导已启动控制面板配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="0bed2-126">The Profile Wizard was launched by the Control Panel configuration application.</span></span> 
    
<span data-ttu-id="0bed2-127">MAPI_PW_PROVIDER_UI_ONLY</span><span class="sxs-lookup"><span data-stu-id="0bed2-127">MAPI_PW_PROVIDER_UI_ONLY</span></span> 
  
> <span data-ttu-id="0bed2-128">应显示仅服务提供商的配置对话框，并不应出现配置文件向导的页面。</span><span class="sxs-lookup"><span data-stu-id="0bed2-128">Only the service providers's configuration dialog boxes should be displayed and the Profile Wizard's pages should not appear.</span></span> <span data-ttu-id="0bed2-129">如果设置了 MAPI_PW_ADD_SERVICE_ONLY 标志，则仅可以设置此标志。</span><span class="sxs-lookup"><span data-stu-id="0bed2-129">This flag can only be set if the MAPI_PW_ADD_SERVICE_ONLY flag is set.</span></span> 
    
 <span data-ttu-id="0bed2-130">_lppszServiceNameToAdd_</span><span class="sxs-lookup"><span data-stu-id="0bed2-130">_lppszServiceNameToAdd_</span></span>
  
> <span data-ttu-id="0bed2-131">[in]指针指向包含消息服务都添加到配置文件的名称的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="0bed2-131">[in] Pointer to an array of strings that contains the names of the message services to be added to the profile.</span></span> <span data-ttu-id="0bed2-132">数组必须终止 NULL 值。</span><span class="sxs-lookup"><span data-stu-id="0bed2-132">The array must terminate with a NULL value.</span></span> 
    
 <span data-ttu-id="0bed2-133">_cbBufferMax_</span><span class="sxs-lookup"><span data-stu-id="0bed2-133">_cbBufferMax_</span></span>
  
> <span data-ttu-id="0bed2-134">[in]_LpszNewProfileName_参数指向缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="0bed2-134">[in] Size of the buffer pointed to by the  _lpszNewProfileName_ parameter.</span></span> 
    
 <span data-ttu-id="0bed2-135">_lpszNewProfileName_</span><span class="sxs-lookup"><span data-stu-id="0bed2-135">_lpszNewProfileName_</span></span>
  
> <span data-ttu-id="0bed2-136">[输出]指向基于**LAUNCHWIZARDENTRY**函数为其返回创建配置文件的名称的字符串缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0bed2-136">[out] Pointer to a string buffer where the function based on **LAUNCHWIZARDENTRY** returns the name of the created profile.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0bed2-137">返回值</span><span class="sxs-lookup"><span data-stu-id="0bed2-137">Return value</span></span>

<span data-ttu-id="0bed2-138">S_OK</span><span class="sxs-lookup"><span data-stu-id="0bed2-138">S_OK</span></span> 
  
> <span data-ttu-id="0bed2-139">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="0bed2-139">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="0bed2-140">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="0bed2-140">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="0bed2-141">意外或未知的原点出现错误，无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="0bed2-141">An error of unexpected or unknown origin prevented the operation from completing.</span></span> <span data-ttu-id="0bed2-142">可能的用途包括未能初始化 MAPI 子系统的配置文件向导，从对话框返回无法访问默认配置文件，而是一个错误。</span><span class="sxs-lookup"><span data-stu-id="0bed2-142">Possibilities include failure to initialize the MAPI subsystem for the Profile Wizard, inability to access the default profile, and an error return from the dialog box.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0bed2-143">说明</span><span class="sxs-lookup"><span data-stu-id="0bed2-143">Remarks</span></span>

<span data-ttu-id="0bed2-144">**LAUNCHWIZARDENTRY**函数原型的 MAPI 实现的 MAPI 配置文件向导应用程序的入口点。</span><span class="sxs-lookup"><span data-stu-id="0bed2-144">The MAPI implementation of the **LAUNCHWIZARDENTRY** function prototype is the entry point into the MAPI Profile Wizard application.</span></span> <span data-ttu-id="0bed2-145">MAPI 命名**LaunchWizard**此入口点。</span><span class="sxs-lookup"><span data-stu-id="0bed2-145">MAPI names this entry point **LaunchWizard**.</span></span> 
  
<span data-ttu-id="0bed2-146">当 MAPI_PW_ADD_SERVICE_ONLY 标志设置_ulFlags_参数中时，下列规则适用：</span><span class="sxs-lookup"><span data-stu-id="0bed2-146">When the MAPI_PW_ADD_SERVICE_ONLY flag is set in the  _ulFlags_ parameter, the following rules apply:</span></span> 
  
- <span data-ttu-id="0bed2-147">MAPI_PW_LAUNCHED_BY_CONFIG 标志禁止显示欢迎页。</span><span class="sxs-lookup"><span data-stu-id="0bed2-147">The MAPI_PW_LAUNCHED_BY_CONFIG flag inhibits the welcome page from being displayed.</span></span> 
    
- <span data-ttu-id="0bed2-148">仅当没有默认配置文件时，MAPI_PW_HIDE_SERVICES_LIST 和 MAPI_PW_PROVIDER_UI_ONLY 标志是很有用。</span><span class="sxs-lookup"><span data-stu-id="0bed2-148">The MAPI_PW_HIDE_SERVICES_LIST and MAPI_PW_PROVIDER_UI_ONLY flags are useful only when there is no default profile.</span></span> <span data-ttu-id="0bed2-149">在这种情况下这些标志确定页是要显示哪些配置文件向导。</span><span class="sxs-lookup"><span data-stu-id="0bed2-149">In this case these flags determine which Profile Wizard page is to be displayed.</span></span> 
    
- <span data-ttu-id="0bed2-150">如果存在默认配置文件，配置文件向导页都将显示。</span><span class="sxs-lookup"><span data-stu-id="0bed2-150">If a default profile exists, none of the Profile Wizard pages are to be displayed.</span></span> 
    
- <span data-ttu-id="0bed2-151">如果存在默认配置文件，只有一个邮件服务列出通过_lppszServiceNameToAdd_参数，并且邮件服务已存在于默认配置文件中，配置文件向导不到配置文件中添加任何返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0bed2-151">If a default profile exists, only one message service is listed through the  _lppszServiceNameToAdd_ parameter, and that message service is already in the default profile, the Profile Wizard returns S_OK without adding anything to the profile.</span></span> 
    
<span data-ttu-id="0bed2-152">对于要添加到配置文件中每个邮件服务，配置文件向导调用基于[MSGSERVICEENTRY](msgserviceentry.md)原型服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="0bed2-152">For every message service to be added to the profile, the Profile Wizard calls the service's entry point function based on the [MSGSERVICEENTRY](msgserviceentry.md) prototype.</span></span> <span data-ttu-id="0bed2-153">从邮件服务中选择要添加到配置文件的每个服务提供商，对于配置文件向导调用基于[WIZARDENTRY](wizardentry.md)原型的提供程序的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="0bed2-153">For each service provider selected from a message service to be added to the profile, the Profile Wizard calls the provider's entry point function based on the [WIZARDENTRY](wizardentry.md) prototype.</span></span> <span data-ttu-id="0bed2-154">交互式配置过程中在属性页中每个用户事件导致配置文件向导来调用基于[SERVICEWIZARDDLGPROC](servicewizarddlgproc.md)原型的提供程序的回调函数。</span><span class="sxs-lookup"><span data-stu-id="0bed2-154">During interactive configuration, every user event in the property pages causes the Profile Wizard to call the provider's callback function based on the [SERVICEWIZARDDLGPROC](servicewizarddlgproc.md) prototype.</span></span> 
  
<span data-ttu-id="0bed2-155">如果要添加到配置文件服务提供商支持的配置文件向导页面，它必须允许编程对配置文件配置。</span><span class="sxs-lookup"><span data-stu-id="0bed2-155">If a service provider being added to the profile supports the Profile Wizard pages, it must allow programmatic configuration of the profile.</span></span>
  

