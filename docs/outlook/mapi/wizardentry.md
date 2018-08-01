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
ms.openlocfilehash: 2c307d18c5b62e5190aa10632a47a3f16b80e81f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779095"
---
# <a name="wizardentry"></a><span data-ttu-id="84213-103">WIZARDENTRY</span><span class="sxs-lookup"><span data-stu-id="84213-103">WIZARDENTRY</span></span>

  
  
<span data-ttu-id="84213-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="84213-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="84213-105">定义种服务提供程序入口点函数，其配置文件向导调用来检索足够的信息来显示提供程序的配置属性表。</span><span class="sxs-lookup"><span data-stu-id="84213-105">Defines a service provider entry point function which the Profile Wizard calls to retrieve enough information to display the provider's configuration property sheets.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="84213-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="84213-106">Header file:</span></span>  <br/> |<span data-ttu-id="84213-107">Mapiwz.h</span><span class="sxs-lookup"><span data-stu-id="84213-107">Mapiwz.h</span></span>  <br/> |
|<span data-ttu-id="84213-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="84213-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="84213-109">服务提供商</span><span class="sxs-lookup"><span data-stu-id="84213-109">Service providers</span></span>  <br/> |
|<span data-ttu-id="84213-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="84213-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="84213-111">MAPI 配置文件向导</span><span class="sxs-lookup"><span data-stu-id="84213-111">MAPI Profile Wizard</span></span>  <br/> |
   
```cpp
ULONG WIZARDENTRY(
  HINSTANCE hProviderDLLInstance,
  LPSTR FAR * lpcsResourceName,
  DLGPROC FAR * lppDlgProc,
  LPMAPIPROP lpMAPIProp,
  LPMAPISUPPORTOBJECT lpMapiSupportObject
);
```

## <a name="parameters"></a><span data-ttu-id="84213-112">参数</span><span class="sxs-lookup"><span data-stu-id="84213-112">Parameters</span></span>

 <span data-ttu-id="84213-113">_hProviderDLLInstance_</span><span class="sxs-lookup"><span data-stu-id="84213-113">_hProviderDLLInstance_</span></span>
  
> <span data-ttu-id="84213-114">[in]服务提供商的 DLL 实例句柄。</span><span class="sxs-lookup"><span data-stu-id="84213-114">[in] Instance handle of the service provider's DLL.</span></span> 
    
 <span data-ttu-id="84213-115">_lpcsResourceName_</span><span class="sxs-lookup"><span data-stu-id="84213-115">_lpcsResourceName_</span></span>
  
> <span data-ttu-id="84213-116">[输出]指针指向包含配置过程中配置文件向导应显示对话框资源的完整名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="84213-116">[out] Pointer to a string that contains the full name of the dialog resource that should be displayed by the Profile Wizard during configuration.</span></span> <span data-ttu-id="84213-117">字符串，包括 NULL 终止符，最大大小为 32 个字符。</span><span class="sxs-lookup"><span data-stu-id="84213-117">The maximum size of the string, including the NULL terminator, is 32 characters.</span></span> 
    
 <span data-ttu-id="84213-118">_lppDlgProc_</span><span class="sxs-lookup"><span data-stu-id="84213-118">_lppDlgProc_</span></span>
  
> <span data-ttu-id="84213-119">[输出]指向标准 Windows 对话框过程将由配置文件向导来通知的提供程序的各种事件调用的指针。</span><span class="sxs-lookup"><span data-stu-id="84213-119">[out] Pointer to a standard Windows dialog box procedure that will be called by the Profile Wizard to notify the provider of various events.</span></span> 
    
 <span data-ttu-id="84213-120">_lpMAPIProp_</span><span class="sxs-lookup"><span data-stu-id="84213-120">_lpMAPIProp_</span></span>
  
> <span data-ttu-id="84213-121">[in]提供对的配置属性访问属性接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="84213-121">[in] Pointer to a property interface implementation that provides access to the configuration properties.</span></span> 
    
 <span data-ttu-id="84213-122">_lpMapiSupportObject_</span><span class="sxs-lookup"><span data-stu-id="84213-122">_lpMapiSupportObject_</span></span>
  
> <span data-ttu-id="84213-123">[in]指向适用于此会话的 MAPI 支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="84213-123">[in] Pointer to the MAPI support object applicable to this session.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="84213-124">返回值</span><span class="sxs-lookup"><span data-stu-id="84213-124">Return value</span></span>

<span data-ttu-id="84213-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="84213-125">S_OK</span></span> 
  
> <span data-ttu-id="84213-126">成功调用了服务提供商的**WIZARDENTRY**函数。</span><span class="sxs-lookup"><span data-stu-id="84213-126">The service provider's **WIZARDENTRY** function was called successfully.</span></span> 
    
<span data-ttu-id="84213-127">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="84213-127">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="84213-128">意外或未知的原点出现错误，无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="84213-128">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="84213-129">说明</span><span class="sxs-lookup"><span data-stu-id="84213-129">Remarks</span></span>

<span data-ttu-id="84213-130">配置文件向导调用**WIZARDENTRY**基于函数，以显示服务提供商的配置用户界面的准备就绪时。</span><span class="sxs-lookup"><span data-stu-id="84213-130">The Profile Wizard calls the **WIZARDENTRY** based function when it is ready to display the service provider's configuration user interface.</span></span> <span data-ttu-id="84213-131">完成配置所有提供程序配置文件向导后，它将通过调用[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)到配置文件写入的配置属性。</span><span class="sxs-lookup"><span data-stu-id="84213-131">When the Profile Wizard is finished configuring all providers, it writes the configuration properties to the profile by calling [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md).</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="84213-132">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="84213-132">Notes to implementers</span></span>

<span data-ttu-id="84213-133">必须在 MAPISVC.INF WIZARD_ENTRY_NAME 条目中放置**WIZARDENTRY**基于函数的名称。</span><span class="sxs-lookup"><span data-stu-id="84213-133">The name of the **WIZARDENTRY** based function must be placed in the WIZARD_ENTRY_NAME entry in MAPISVC.INF.</span></span> 
  
<span data-ttu-id="84213-134">资源名称是对话框资源的将呈现窗格中的配置文件向导。</span><span class="sxs-lookup"><span data-stu-id="84213-134">The resource name is that of the dialog resource that will be rendered in the pane of the Profile Wizard.</span></span> <span data-ttu-id="84213-135">传递后需要包含单个对话框资源中的所有页面的资源。</span><span class="sxs-lookup"><span data-stu-id="84213-135">The resource that is passed back needs to contain all the pages in a single dialog resource.</span></span> <span data-ttu-id="84213-136">当配置文件向导收到此资源时，它将忽略该对话框样式，但不是的控件样式，并作为子级的配置文件向导页上创建的所有控件。</span><span class="sxs-lookup"><span data-stu-id="84213-136">When the Profile Wizard receives this resource, it ignores the dialog style, but not the control styles, and creates all the controls as children of the Profile Wizard page.</span></span> <span data-ttu-id="84213-137">所有控件最初处于隐藏都状态。</span><span class="sxs-lookup"><span data-stu-id="84213-137">All controls are initially hidden.</span></span> <span data-ttu-id="84213-138">提供程序应进行确保其控件的坐标都零或从零开始，，它们不超过 200 个对话框单位的最大宽度和 150 个对话框单位的最大高度。</span><span class="sxs-lookup"><span data-stu-id="84213-138">Providers should make sure that the coordinates for their controls are zero or zero-based, and that they do not exceed a maximum width of 200 dialog units and a maximum height of 150 dialog units.</span></span> <span data-ttu-id="84213-139">下面的 400 控件标识符被保留，供配置文件向导。</span><span class="sxs-lookup"><span data-stu-id="84213-139">Control identifiers below 400 are reserved for the Profile Wizard.</span></span> <span data-ttu-id="84213-140">配置文件向导加粗文本上方提供程序的用户界面中显示的提供程序的标题。</span><span class="sxs-lookup"><span data-stu-id="84213-140">The Profile Wizard displays the provider's title in bold text above the provider's user interface.</span></span> 
  
<span data-ttu-id="84213-141">_LpMAPIProp_参数中提供的属性接口指针应保留以供将来参考服务提供商。</span><span class="sxs-lookup"><span data-stu-id="84213-141">The property interface pointer supplied in the  _lpMAPIProp_ parameter should be retained by the provider for future reference.</span></span> <span data-ttu-id="84213-142">配置文件向导处理仅最基本的一组属性，并提供程序可以使用该属性接口实现包括其他属性。</span><span class="sxs-lookup"><span data-stu-id="84213-142">The Profile Wizard deals with only the most basic set of properties, and the provider can use the property interface implementation to include additional properties.</span></span> <span data-ttu-id="84213-143">在配置期间，提供程序应将其配置属性添加到实现属性接口的对象。</span><span class="sxs-lookup"><span data-stu-id="84213-143">During configuration, providers should add their configuration properties to the object implementing the property interface.</span></span> <span data-ttu-id="84213-144">已配置的所有提供商之后，配置文件向导会将这些属性添加到配置文件。</span><span class="sxs-lookup"><span data-stu-id="84213-144">After all providers have been configured, the Profile Wizard adds these properties to the profile.</span></span> 
  
<span data-ttu-id="84213-145">有关如何使用此函数的详细信息，请参阅[支持的消息服务配置](supporting-message-service-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="84213-145">For more information about how to use this function, see [Supporting Message Service Configuration](supporting-message-service-configuration.md).</span></span> 
  

