---
title: MSGSERVICEENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MSGSERVICEENTRY
api_type:
- COM
ms.assetid: 655774a6-588c-44c7-903b-4497b7eccbc2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 56a5f153dbd563397b9216af32a715692d0876d7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427876"
---
# <a name="msgserviceentry"></a><span data-ttu-id="2fce6-103">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="2fce6-103">MSGSERVICEENTRY</span></span>

  
  
<span data-ttu-id="2fce6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2fce6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2fce6-105">定义用于支持邮件服务配置的邮件服务入口点函数的原型。</span><span class="sxs-lookup"><span data-stu-id="2fce6-105">Defines a prototype for a message service entry point function to support message service configuration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2fce6-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2fce6-106">Header file:</span></span>  <br/> |<span data-ttu-id="2fce6-107">Mapispi</span><span class="sxs-lookup"><span data-stu-id="2fce6-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="2fce6-108">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="2fce6-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="2fce6-109">邮件服务</span><span class="sxs-lookup"><span data-stu-id="2fce6-109">Message services</span></span>  <br/> |
|<span data-ttu-id="2fce6-110">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="2fce6-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="2fce6-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="2fce6-111">MAPI</span></span>  <br/> |
   
```cpp
HRESULT MSGSERVICEENTRY(
  HINSTANCE hInstance,
  LPMALLOC lpMalloc,
  LPMAPISUP lpMAPISup,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG ulContext,
  ULONG cValues,
  LPSPropValue lpProps,
  LPPROVIDERADMIN lpProviderAdmin,
  LPMAPIERROR FAR * lppMapiError
);
```

## <a name="parameters"></a><span data-ttu-id="2fce6-112">参数</span><span class="sxs-lookup"><span data-stu-id="2fce6-112">Parameters</span></span>

 <span data-ttu-id="2fce6-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="2fce6-113">_hInstance_</span></span>
  
> <span data-ttu-id="2fce6-114">实时服务 providerDLL 的实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="2fce6-114">[in] Handle of the instance of the service providerDLL.</span></span> <span data-ttu-id="2fce6-115">该句柄通常用于检索资源。</span><span class="sxs-lookup"><span data-stu-id="2fce6-115">The handle is typically used to retrieve resources.</span></span> 
    
 <span data-ttu-id="2fce6-116">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="2fce6-116">_lpMalloc_</span></span>
  
> <span data-ttu-id="2fce6-117">实时指向用于公开 OLE **IMalloc**接口的内存分配器对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2fce6-117">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="2fce6-118">在使用某些接口 (如**IStream**) 时, 邮件服务可能需要使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="2fce6-118">The message service may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="2fce6-119">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="2fce6-119">_lpMAPISup_</span></span>
  
> <span data-ttu-id="2fce6-120">实时指向 IMAPISupport 的指针[: IUnknown](imapisupportiunknown.md)接口实现。</span><span class="sxs-lookup"><span data-stu-id="2fce6-120">[in] Pointer to an [IMAPISupport : IUnknown](imapisupportiunknown.md) interface implementation.</span></span> 
    
 <span data-ttu-id="2fce6-121">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="2fce6-121">_ulUIParam_</span></span>
  
> <span data-ttu-id="2fce6-122">实时用于将用户界面信息传递给函数或零的特定于实现的值。</span><span class="sxs-lookup"><span data-stu-id="2fce6-122">[in] An implementation-specific value used for passing user interface information to a function or zero.</span></span> <span data-ttu-id="2fce6-123">_ulUIParam_参数是 "配置" 对话框的父窗口句柄, 其类型为 HWND (转换为 ULONG_PTR)。</span><span class="sxs-lookup"><span data-stu-id="2fce6-123">The  _ulUIParam_ parameter is the parent window handle for the configuration dialog box and is of type HWND (cast to a ULONG_PTR).</span></span> <span data-ttu-id="2fce6-124">如果值为零, 则表示没有父窗口。</span><span class="sxs-lookup"><span data-stu-id="2fce6-124">A value of zero indicates that there is no parent window.</span></span> 
    
 <span data-ttu-id="2fce6-125">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2fce6-125">_ulFlags_</span></span>
  
> <span data-ttu-id="2fce6-126">实时指示服务输入函数选项的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2fce6-126">[in] Bitmask of flags indicating options for the service entry function.</span></span> <span data-ttu-id="2fce6-127">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="2fce6-127">The following flags can be set:</span></span>
    
<span data-ttu-id="2fce6-128">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2fce6-128">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="2fce6-129">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="2fce6-129">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="2fce6-130">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="2fce6-130">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
<span data-ttu-id="2fce6-131">MSG_SERVICE_UI_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="2fce6-131">MSG_SERVICE_UI_READ_ONLY</span></span> 
  
> <span data-ttu-id="2fce6-132">服务的配置用户界面应显示当前配置, 但不允许用户对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="2fce6-132">The service's configuration user interface should display the current configuration but not allow the user to change it.</span></span> 
    
<span data-ttu-id="2fce6-133">SERVICE_UI_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="2fce6-133">SERVICE_UI_ALLOWED</span></span> 
  
> <span data-ttu-id="2fce6-134">允许显示配置对话框 (如有必要)。</span><span class="sxs-lookup"><span data-stu-id="2fce6-134">Permits a configuration dialog box to be displayed if necessary.</span></span> <span data-ttu-id="2fce6-135">设置 SERVICE_UI_ALLOWED 标志后, 仅当_lpProps_属性值数组为空或不包含有效配置时, 才应显示对话框。</span><span class="sxs-lookup"><span data-stu-id="2fce6-135">When the SERVICE_UI_ALLOWED flag is set, the dialog box should be displayed only if the  _lpProps_ property value array is empty or does not contain a valid configuration.</span></span> <span data-ttu-id="2fce6-136">如果未设置 SERVICE_UI_ALLOWED, 则在设置 SERVICE_UI_ALWAYS 标志的情况下, 可能仍会显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="2fce6-136">If SERVICE_UI_ALLOWED is not set, a dialog box might still be displayed if the SERVICE_UI_ALWAYS flag is set.</span></span> 
    
<span data-ttu-id="2fce6-137">UI_CURRENT_PROVIDER_FIRST</span><span class="sxs-lookup"><span data-stu-id="2fce6-137">UI_CURRENT_PROVIDER_FIRST</span></span> 
  
> <span data-ttu-id="2fce6-138">请求活动提供程序的 "配置" 对话框显示在其他对话框的上方。</span><span class="sxs-lookup"><span data-stu-id="2fce6-138">Requests that the configuration dialog box for the active provider be displayed on top of other dialog boxes.</span></span> 
    
<span data-ttu-id="2fce6-139">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="2fce6-139">SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="2fce6-140">需要邮件服务显示 "配置" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2fce6-140">Requires the message service to display a configuration dialog box.</span></span> <span data-ttu-id="2fce6-141">如果未设置 SERVICE_UI_ALWAYS 标志, 则在设置了 SERVICE_UI_ALLOWED 标志且在_lpProps_属性值数组中不提供有效的配置信息的情况下, 可能仍会显示 "配置" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2fce6-141">If the SERVICE_UI_ALWAYS flag is not set, a configuration dialog box might still be displayed if the SERVICE_UI_ALLOWED flag is set and valid configuration information is not available from the  _lpProps_ property value array.</span></span> <span data-ttu-id="2fce6-142">必须将 SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 设置为允许显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="2fce6-142">Either SERVICE_UI_ALLOWED or SERVICE_UI_ALWAYS must be set to allow a user interface to be displayed.</span></span> 
    
 <span data-ttu-id="2fce6-143">_ulContext_</span><span class="sxs-lookup"><span data-stu-id="2fce6-143">_ulContext_</span></span>
  
> <span data-ttu-id="2fce6-144">实时MAPI 当前正在执行的配置操作。</span><span class="sxs-lookup"><span data-stu-id="2fce6-144">[in] The configuration operation that MAPI is currently performing.</span></span> <span data-ttu-id="2fce6-145">_ulContext_参数将包含以下值之一:</span><span class="sxs-lookup"><span data-stu-id="2fce6-145">The  _ulContext_ parameter will contain one of the following values:</span></span> 
    
<span data-ttu-id="2fce6-146">MSG_SERVICE_CONFIGURE</span><span class="sxs-lookup"><span data-stu-id="2fce6-146">MSG_SERVICE_CONFIGURE</span></span> 
  
> <span data-ttu-id="2fce6-147">应在配置文件中进行对服务配置的更改。</span><span class="sxs-lookup"><span data-stu-id="2fce6-147">Changes to the service's configuration should be made in the profile.</span></span> <span data-ttu-id="2fce6-148">如果设置了 SERVICE_UI_ALWAYS 标志, 则服务应显示其 "配置" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2fce6-148">If the SERVICE_UI_ALWAYS flag is set, the service should display its configuration dialog box.</span></span> <span data-ttu-id="2fce6-149">如果设置了 SERVICE_UI_ALLOWED 标志, 并且_lpProps_参数为空或不包含有效的配置数据, 也应显示对话框。</span><span class="sxs-lookup"><span data-stu-id="2fce6-149">The dialog box should also be displayed if the SERVICE_UI_ALLOWED flag is set and the  _lpProps_ parameter is empty or does not contain valid configuration data.</span></span> <span data-ttu-id="2fce6-150">如果_lpProps_包含有效数据, 则不应显示任何对话框, 并且该服务应使用此数据进行配置更改。</span><span class="sxs-lookup"><span data-stu-id="2fce6-150">If  _lpProps_ contains valid data, no dialog box should be displayed and the service should use this data for making the configuration change.</span></span> 
    
<span data-ttu-id="2fce6-151">MSG_SERVICE_CREATE</span><span class="sxs-lookup"><span data-stu-id="2fce6-151">MSG_SERVICE_CREATE</span></span> 
  
> <span data-ttu-id="2fce6-152">正在将服务添加到配置文件。</span><span class="sxs-lookup"><span data-stu-id="2fce6-152">The service is being added to a profile.</span></span> <span data-ttu-id="2fce6-153">如果设置了 SERVICE_UI_ALWAYS 或 SERVICE_UI_ALLOWED 标志, 则该服务应显示其 "配置" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2fce6-153">If either the SERVICE_UI_ALWAYS or SERVICE_UI_ALLOWED flag is set, the service should display its configuration dialog box.</span></span> <span data-ttu-id="2fce6-154">如果两个标志都未设置, 则服务应失败。</span><span class="sxs-lookup"><span data-stu-id="2fce6-154">If neither flag is set, the service should fail.</span></span> 
    
<span data-ttu-id="2fce6-155">MSG_SERVICE_DELETE</span><span class="sxs-lookup"><span data-stu-id="2fce6-155">MSG_SERVICE_DELETE</span></span> 
  
> <span data-ttu-id="2fce6-156">正在从配置文件中删除该服务。</span><span class="sxs-lookup"><span data-stu-id="2fce6-156">The service is being removed from a profile.</span></span> <span data-ttu-id="2fce6-157">在收到此事件之后, 服务应返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="2fce6-157">After receiving this event, the service should return S_OK.</span></span>
    
<span data-ttu-id="2fce6-158">MSG_SERVICE_INSTALL</span><span class="sxs-lookup"><span data-stu-id="2fce6-158">MSG_SERVICE_INSTALL</span></span> 
  
> <span data-ttu-id="2fce6-159">已从网络、软盘或其他外部媒体将该服务安装到用户的工作站上。</span><span class="sxs-lookup"><span data-stu-id="2fce6-159">The service has been installed to the user's workstation from a network, floppy disk, or other external medium.</span></span> <span data-ttu-id="2fce6-160">在收到此事件之后, 服务通常返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="2fce6-160">After receiving this event, the service usually returns S_OK.</span></span> 
    
<span data-ttu-id="2fce6-161">MSG_SERVICE_PROVIDER_CREATE</span><span class="sxs-lookup"><span data-stu-id="2fce6-161">MSG_SERVICE_PROVIDER_CREATE</span></span> 
  
> <span data-ttu-id="2fce6-162">请求服务创建提供程序的其他实例。</span><span class="sxs-lookup"><span data-stu-id="2fce6-162">Requests that the service create an additional instance of a provider.</span></span> <span data-ttu-id="2fce6-163">如果服务支持此操作, 则应调用[IProviderAdmin:: CreateProvider](iprovideradmin-createprovider.md)。</span><span class="sxs-lookup"><span data-stu-id="2fce6-163">If the service supports this operation, it should call [IProviderAdmin::CreateProvider](iprovideradmin-createprovider.md).</span></span> <span data-ttu-id="2fce6-164">如果服务不支持此操作, 则可以返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="2fce6-164">If the service does not support this operation, it can return MAPI_E_NO_SUPPORT.</span></span> 
    
<span data-ttu-id="2fce6-165">MSG_SERVICE_PROVIDER_DELETE</span><span class="sxs-lookup"><span data-stu-id="2fce6-165">MSG_SERVICE_PROVIDER_DELETE</span></span> 
  
> <span data-ttu-id="2fce6-166">请求服务删除提供程序实例。</span><span class="sxs-lookup"><span data-stu-id="2fce6-166">Requests that the service delete a provider instance.</span></span> <span data-ttu-id="2fce6-167">如果服务支持此操作, 则应调用[IProviderAdmin::D eleteprovider](iprovideradmin-deleteprovider.md)。</span><span class="sxs-lookup"><span data-stu-id="2fce6-167">If the service supports this operation, it should call [IProviderAdmin::DeleteProvider](iprovideradmin-deleteprovider.md).</span></span> <span data-ttu-id="2fce6-168">如果服务不支持此操作, 则可以返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="2fce6-168">If the service does not support this operation, it can return MAPI_E_NO_SUPPORT.</span></span>
    
<span data-ttu-id="2fce6-169">MSG_SERVICE_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="2fce6-169">MSG_SERVICE_UNINSTALL</span></span> 
  
> <span data-ttu-id="2fce6-170">正在删除服务。</span><span class="sxs-lookup"><span data-stu-id="2fce6-170">The service is being removed.</span></span> <span data-ttu-id="2fce6-171">在收到此事件之后, 服务可以执行任何应在服务结束之前完成的清理任务, 然后返回成功值。</span><span class="sxs-lookup"><span data-stu-id="2fce6-171">After receiving this event, the service can perform any cleanup tasks that should be done before the service ends and then return with a success value.</span></span> <span data-ttu-id="2fce6-172">如果用户取消了删除操作, 服务应返回 MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="2fce6-172">If the user cancels the removal, the service should return MAPI_E_USER_CANCEL.</span></span> 
    
 <span data-ttu-id="2fce6-173">_cValues_</span><span class="sxs-lookup"><span data-stu-id="2fce6-173">_cValues_</span></span>
  
> <span data-ttu-id="2fce6-174">实时由_lpProps_参数指向的数组中的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="2fce6-174">[in] Count of property values in the array pointed to by the  _lpProps_ parameter.</span></span> <span data-ttu-id="2fce6-175">如果 MAPI 不传递属性值, 则_cValues_参数的值为零。</span><span class="sxs-lookup"><span data-stu-id="2fce6-175">The value of the  _cValues_ parameter is zero if MAPI is passing no property values.</span></span> 
    
 <span data-ttu-id="2fce6-176">_lpProps_</span><span class="sxs-lookup"><span data-stu-id="2fce6-176">_lpProps_</span></span>
  
> <span data-ttu-id="2fce6-177">实时指向[SPropValue](spropvalue.md)结构的可选数组的指针, 该数组指示函数将在配置消息服务时使用的提供程序支持属性的值。</span><span class="sxs-lookup"><span data-stu-id="2fce6-177">[in] Pointer to an optional array of [SPropValue](spropvalue.md) structures indicating values for provider-supported properties that the function will use in configuring the message service.</span></span> <span data-ttu-id="2fce6-178">如果将_ulContext_参数设置为 MSG_SERVICE_CONFIGURE, 则此函数仅使用此参数。</span><span class="sxs-lookup"><span data-stu-id="2fce6-178">The function only uses this parameter if the  _ulContext_ parameter is set to MSG_SERVICE_CONFIGURE.</span></span> <span data-ttu-id="2fce6-179">此参数通常用于将路径传递到基于文件的服务 (如个人通讯簿服务) 的文件。</span><span class="sxs-lookup"><span data-stu-id="2fce6-179">This parameter is commonly used to pass the path to a file for a file-based service, such as a personal address book service.</span></span> <span data-ttu-id="2fce6-180">如果未在_ulFlags_参数中传递 MSG_SERVICE_CONFIGURE 标志, 则_lpProps_参数必须为零。</span><span class="sxs-lookup"><span data-stu-id="2fce6-180">If the MSG_SERVICE_CONFIGURE flag is not passed in the  _ulFlags_ parameter, the  _lpProps_ parameter must be zero.</span></span> 
    
 <span data-ttu-id="2fce6-181">_lpProviderAdmin_</span><span class="sxs-lookup"><span data-stu-id="2fce6-181">_lpProviderAdmin_</span></span>
  
> <span data-ttu-id="2fce6-182">实时指向[IProviderAdmin: IUnknown](iprovideradminiunknown.md)接口的指针, 该函数可使用该接口为当前邮件服务中的特定提供程序定位配置文件节。</span><span class="sxs-lookup"><span data-stu-id="2fce6-182">[in] Pointer to an [IProviderAdmin:IUnknown](iprovideradminiunknown.md) interface that the function can use to locate profile sections for a specific provider in the current message service.</span></span> 
    
 <span data-ttu-id="2fce6-183">_lppMapiError_</span><span class="sxs-lookup"><span data-stu-id="2fce6-183">_lppMapiError_</span></span>
  
> <span data-ttu-id="2fce6-184">排除指向[MAPIERROR](mapierror.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="2fce6-184">[out] Pointer to a [MAPIERROR](mapierror.md) structure.</span></span> <span data-ttu-id="2fce6-185">结构是使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数分配的。</span><span class="sxs-lookup"><span data-stu-id="2fce6-185">The structure is allocated with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> <span data-ttu-id="2fce6-186">所有成员都是可选的, 但大多数结构将包含_lpszError_成员中的有效错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="2fce6-186">All members are optional, although most structures will contain a valid error message string in the  _lpszError_ member.</span></span> <span data-ttu-id="2fce6-187">如果存在结构的_lpszComponent_或_lpszError_成员, 则它们的内存最终必须通过对基础结构上的[MAPIFreeBuffer](mapifreebuffer.md)的单个调用来释放。</span><span class="sxs-lookup"><span data-stu-id="2fce6-187">If the  _lpszComponent_ or  _lpszError_ members of the structure are present, their memory must eventually be freed by a single call to [MAPIFreeBuffer](mapifreebuffer.md) on the base structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2fce6-188">返回值</span><span class="sxs-lookup"><span data-stu-id="2fce6-188">Return value</span></span>

<span data-ttu-id="2fce6-189">S_OK</span><span class="sxs-lookup"><span data-stu-id="2fce6-189">S_OK</span></span> 
  
> <span data-ttu-id="2fce6-190">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="2fce6-190">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="2fce6-191">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="2fce6-191">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="2fce6-192">尚未配置服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="2fce6-192">The service provider has not been configured.</span></span> 
    
<span data-ttu-id="2fce6-193">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="2fce6-193">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="2fce6-194">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2fce6-194">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
<span data-ttu-id="2fce6-195">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2fce6-195">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="2fce6-196">提供程序不支持对其对象的更改或不支持更改通知。</span><span class="sxs-lookup"><span data-stu-id="2fce6-196">The provider either does not support changes to its objects or does not support notification of changes.</span></span> 
    
<span data-ttu-id="2fce6-197">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="2fce6-197">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="2fce6-198">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="2fce6-198">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation only supports Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2fce6-199">说明</span><span class="sxs-lookup"><span data-stu-id="2fce6-199">Remarks</span></span>

<span data-ttu-id="2fce6-200">使用**MSGSERVICEENTRY**函数原型定义的函数使邮件服务能够自行配置或执行其他特定于服务的操作。</span><span class="sxs-lookup"><span data-stu-id="2fce6-200">A function defined using the **MSGSERVICEENTRY** function prototype enables message services to configure themselves or to perform other service-specific actions.</span></span> <span data-ttu-id="2fce6-201">该函数主要提供一个对话框, 用户可以在其中更改特定于邮件服务的设置。</span><span class="sxs-lookup"><span data-stu-id="2fce6-201">The function primarily furnishes a dialog box in which the user can change settings specific to the message service.</span></span> <span data-ttu-id="2fce6-202">它还可以使用在_lpProps_参数中传递的属性值数组支持编程配置。</span><span class="sxs-lookup"><span data-stu-id="2fce6-202">It can also support programmatic configuration by using the property value array passed in the  _lpProps_ parameter.</span></span> <span data-ttu-id="2fce6-203">编程配置是可选的, 除非服务支持配置文件向导 (需要它)。</span><span class="sxs-lookup"><span data-stu-id="2fce6-203">Programmatic configuration is optional unless the service supports the Profile Wizard, for which it is required.</span></span> 
  
<span data-ttu-id="2fce6-204">MAPI 从 "控制面板" 应用程序或响应调用[IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md)或[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)的客户端应用程序调用此入口点。</span><span class="sxs-lookup"><span data-stu-id="2fce6-204">MAPI calls this entry point from the Control Panel application or in response to a client application calling [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) or [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md).</span></span> 
  
<span data-ttu-id="2fce6-205">MAPI 对邮件服务对**MSGSERVICEENTRY**原型使用的函数名称没有限制, 但优先于名称**ServiceEntry**。</span><span class="sxs-lookup"><span data-stu-id="2fce6-205">MAPI places no restriction on the function name that a message service uses for the **MSGSERVICEENTRY** prototype but prefers the name **ServiceEntry**.</span></span> <span data-ttu-id="2fce6-206">函数的序号没有限制, 并且单个提供程序 DLL 可以包含多个函数。</span><span class="sxs-lookup"><span data-stu-id="2fce6-206">There is no restriction on the ordinal for the function, and a single provider DLL can contain more than one function.</span></span> <span data-ttu-id="2fce6-207">但是, 其中只有一个函数可命名为**ServiceEntry**。</span><span class="sxs-lookup"><span data-stu-id="2fce6-207">However, only one of the functions can be named **ServiceEntry**.</span></span> 
  
<span data-ttu-id="2fce6-208">邮件服务可以使用[BuildDisplayTable](builddisplaytable.md)函数和[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法来简化配置对话框的实现。</span><span class="sxs-lookup"><span data-stu-id="2fce6-208">A message service can use the [BuildDisplayTable](builddisplaytable.md) function and the [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method to simplify configuration dialog box implementation.</span></span> 
  
<span data-ttu-id="2fce6-209">用户可以取消 MSG_SERVICE_UNINSTALL 操作。</span><span class="sxs-lookup"><span data-stu-id="2fce6-209">It is possible for a user to cancel a MSG_SERVICE_UNINSTALL operation.</span></span> <span data-ttu-id="2fce6-210">在这种情况下, **ServiceEntry**函数应与用户进行确认, 以验证是否不应删除服务, 如果服务仍保持安装, 则返回 MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="2fce6-210">In this case, the **ServiceEntry** function should check with the user to verify that the service should not be removed and return MAPI_E_USER_CANCEL if the service remains installed.</span></span> 
  
<span data-ttu-id="2fce6-211">基于**MSGSERVICEENTRY**原型的函数返回列出的 HRESULT 值之一。</span><span class="sxs-lookup"><span data-stu-id="2fce6-211">A function based on the **MSGSERVICEENTRY** prototype returns one of the HRESULT values listed.</span></span> <span data-ttu-id="2fce6-212">当响应客户端对[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)的调用时, MAPI 将转发此值。</span><span class="sxs-lookup"><span data-stu-id="2fce6-212">MAPI forwards this value when responding to a client's call to [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md).</span></span> 
  
<span data-ttu-id="2fce6-213">导出服务条目函数的邮件服务必须在的 "邮件服务" 部分中包含**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 和**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 属性MAPISVC.INF。</span><span class="sxs-lookup"><span data-stu-id="2fce6-213">Message services that export a service entry function must include the **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) and **PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) properties in the message service section of MAPISVC.INF.</span></span> 
  

