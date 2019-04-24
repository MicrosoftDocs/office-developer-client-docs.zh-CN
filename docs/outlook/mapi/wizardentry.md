---
title: WIZARDENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.WIZARDENTRY
api_type:
- COM
ms.assetid: e807c6b5-06cd-4ade-9d9e-69ba6abd1614
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 907984a80dbb6c5464f95def1481d002f9d6638a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329552"
---
# <a name="wizardentry"></a><span data-ttu-id="62b4a-103">WIZARDENTRY</span><span class="sxs-lookup"><span data-stu-id="62b4a-103">WIZARDENTRY</span></span>

  
  
<span data-ttu-id="62b4a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="62b4a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="62b4a-105">定义一个服务提供程序入口点函数, 配置文件向导调用它以检索足够的信息, 以显示提供程序的配置属性表。</span><span class="sxs-lookup"><span data-stu-id="62b4a-105">Defines a service provider entry point function which the Profile Wizard calls to retrieve enough information to display the provider's configuration property sheets.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="62b4a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="62b4a-106">Header file:</span></span>  <br/> |<span data-ttu-id="62b4a-107">Mapiwz</span><span class="sxs-lookup"><span data-stu-id="62b4a-107">Mapiwz.h</span></span>  <br/> |
|<span data-ttu-id="62b4a-108">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="62b4a-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="62b4a-109">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="62b4a-109">Service providers</span></span>  <br/> |
|<span data-ttu-id="62b4a-110">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="62b4a-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="62b4a-111">MAPI 配置文件向导</span><span class="sxs-lookup"><span data-stu-id="62b4a-111">MAPI Profile Wizard</span></span>  <br/> |
   
```cpp
ULONG WIZARDENTRY(
  HINSTANCE hProviderDLLInstance,
  LPSTR FAR * lpcsResourceName,
  DLGPROC FAR * lppDlgProc,
  LPMAPIPROP lpMAPIProp,
  LPMAPISUPPORTOBJECT lpMapiSupportObject
);
```

## <a name="parameters"></a><span data-ttu-id="62b4a-112">参数</span><span class="sxs-lookup"><span data-stu-id="62b4a-112">Parameters</span></span>

 <span data-ttu-id="62b4a-113">_hProviderDLLInstance_</span><span class="sxs-lookup"><span data-stu-id="62b4a-113">_hProviderDLLInstance_</span></span>
  
> <span data-ttu-id="62b4a-114">实时服务提供程序的 DLL 的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="62b4a-114">[in] Instance handle of the service provider's DLL.</span></span> 
    
 <span data-ttu-id="62b4a-115">_lpcsResourceName_</span><span class="sxs-lookup"><span data-stu-id="62b4a-115">_lpcsResourceName_</span></span>
  
> <span data-ttu-id="62b4a-116">排除指向一个字符串的指针, 该字符串包含在配置过程中应由配置文件向导显示的对话框资源的完整名称。</span><span class="sxs-lookup"><span data-stu-id="62b4a-116">[out] Pointer to a string that contains the full name of the dialog resource that should be displayed by the Profile Wizard during configuration.</span></span> <span data-ttu-id="62b4a-117">字符串的最大大小 (包括 NULL 终止符) 为32个字符。</span><span class="sxs-lookup"><span data-stu-id="62b4a-117">The maximum size of the string, including the NULL terminator, is 32 characters.</span></span> 
    
 <span data-ttu-id="62b4a-118">_lppDlgProc_</span><span class="sxs-lookup"><span data-stu-id="62b4a-118">_lppDlgProc_</span></span>
  
> <span data-ttu-id="62b4a-119">排除指向标准 Windows 对话框过程的指针, 该过程将由配置文件向导调用以通知提供程序的各种事件。</span><span class="sxs-lookup"><span data-stu-id="62b4a-119">[out] Pointer to a standard Windows dialog box procedure that will be called by the Profile Wizard to notify the provider of various events.</span></span> 
    
 <span data-ttu-id="62b4a-120">_lpMAPIProp_</span><span class="sxs-lookup"><span data-stu-id="62b4a-120">_lpMAPIProp_</span></span>
  
> <span data-ttu-id="62b4a-121">实时指向提供对配置属性的访问权限的属性接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="62b4a-121">[in] Pointer to a property interface implementation that provides access to the configuration properties.</span></span> 
    
 <span data-ttu-id="62b4a-122">_lpMapiSupportObject_</span><span class="sxs-lookup"><span data-stu-id="62b4a-122">_lpMapiSupportObject_</span></span>
  
> <span data-ttu-id="62b4a-123">实时指向适用于此会话的 MAPI 支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="62b4a-123">[in] Pointer to the MAPI support object applicable to this session.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="62b4a-124">返回值</span><span class="sxs-lookup"><span data-stu-id="62b4a-124">Return value</span></span>

<span data-ttu-id="62b4a-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="62b4a-125">S_OK</span></span> 
  
> <span data-ttu-id="62b4a-126">成功调用服务提供程序的**WIZARDENTRY**函数。</span><span class="sxs-lookup"><span data-stu-id="62b4a-126">The service provider's **WIZARDENTRY** function was called successfully.</span></span> 
    
<span data-ttu-id="62b4a-127">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="62b4a-127">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="62b4a-128">意外或未知来源的错误阻止操作完成。</span><span class="sxs-lookup"><span data-stu-id="62b4a-128">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="62b4a-129">注解</span><span class="sxs-lookup"><span data-stu-id="62b4a-129">Remarks</span></span>

<span data-ttu-id="62b4a-130">"配置文件向导" 在准备好显示服务提供商的配置用户界面时调用基于**WIZARDENTRY**的函数。</span><span class="sxs-lookup"><span data-stu-id="62b4a-130">The Profile Wizard calls the **WIZARDENTRY** based function when it is ready to display the service provider's configuration user interface.</span></span> <span data-ttu-id="62b4a-131">配置文件向导完成配置所有提供程序后, 通过调用[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)将配置属性写入配置文件。</span><span class="sxs-lookup"><span data-stu-id="62b4a-131">When the Profile Wizard is finished configuring all providers, it writes the configuration properties to the profile by calling [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md).</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="62b4a-132">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="62b4a-132">Notes to implementers</span></span>

<span data-ttu-id="62b4a-133">基于**WIZARDENTRY**的函数的名称必须放在 mapisvc.inf 中的 WIZARD_ENTRY_NAME 条目中。</span><span class="sxs-lookup"><span data-stu-id="62b4a-133">The name of the **WIZARDENTRY** based function must be placed in the WIZARD_ENTRY_NAME entry in MAPISVC.INF.</span></span> 
  
<span data-ttu-id="62b4a-134">资源名称是将在 "配置文件向导" 窗格中呈现的对话框资源的名称。</span><span class="sxs-lookup"><span data-stu-id="62b4a-134">The resource name is that of the dialog resource that will be rendered in the pane of the Profile Wizard.</span></span> <span data-ttu-id="62b4a-135">传递回的资源需要包含单个对话框资源中的所有页面。</span><span class="sxs-lookup"><span data-stu-id="62b4a-135">The resource that is passed back needs to contain all the pages in a single dialog resource.</span></span> <span data-ttu-id="62b4a-136">当配置文件向导收到此资源时, 它将忽略对话框样式 (而不是控件样式), 并将所有控件创建为 "配置文件向导" 页的子级。</span><span class="sxs-lookup"><span data-stu-id="62b4a-136">When the Profile Wizard receives this resource, it ignores the dialog style, but not the control styles, and creates all the controls as children of the Profile Wizard page.</span></span> <span data-ttu-id="62b4a-137">所有控件最初都处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="62b4a-137">All controls are initially hidden.</span></span> <span data-ttu-id="62b4a-138">提供程序应确保其控件的坐标为零或从零开始, 并且不超过最大宽度为200的对话框单元, 最大高度为150个对话框单位。</span><span class="sxs-lookup"><span data-stu-id="62b4a-138">Providers should make sure that the coordinates for their controls are zero or zero-based, and that they do not exceed a maximum width of 200 dialog units and a maximum height of 150 dialog units.</span></span> <span data-ttu-id="62b4a-139">低于400的控制标识符是为配置文件向导保留的。</span><span class="sxs-lookup"><span data-stu-id="62b4a-139">Control identifiers below 400 are reserved for the Profile Wizard.</span></span> <span data-ttu-id="62b4a-140">"配置文件向导" 在提供程序的用户界面上方的加粗文本中显示提供程序的标题。</span><span class="sxs-lookup"><span data-stu-id="62b4a-140">The Profile Wizard displays the provider's title in bold text above the provider's user interface.</span></span> 
  
<span data-ttu-id="62b4a-141">_lpMAPIProp_参数中提供的属性接口指针应由提供程序保留, 以供将来参考。</span><span class="sxs-lookup"><span data-stu-id="62b4a-141">The property interface pointer supplied in the  _lpMAPIProp_ parameter should be retained by the provider for future reference.</span></span> <span data-ttu-id="62b4a-142">配置文件向导仅处理最基本的一组属性, 并且提供程序可以使用属性接口实现来包含其他属性。</span><span class="sxs-lookup"><span data-stu-id="62b4a-142">The Profile Wizard deals with only the most basic set of properties, and the provider can use the property interface implementation to include additional properties.</span></span> <span data-ttu-id="62b4a-143">在配置过程中, 提供程序应将其配置属性添加到实现属性接口的对象。</span><span class="sxs-lookup"><span data-stu-id="62b4a-143">During configuration, providers should add their configuration properties to the object implementing the property interface.</span></span> <span data-ttu-id="62b4a-144">配置完所有提供程序后, 配置文件向导会将这些属性添加到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="62b4a-144">After all providers have been configured, the Profile Wizard adds these properties to the profile.</span></span> 
  
<span data-ttu-id="62b4a-145">有关如何使用此函数的详细信息, 请参阅[支持邮件服务配置](supporting-message-service-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="62b4a-145">For more information about how to use this function, see [Supporting Message Service Configuration](supporting-message-service-configuration.md).</span></span> 
  

