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
ms.openlocfilehash: 954609cbc62039c0d60874bde83fde50d1d11c30
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591665"
---
# <a name="msgserviceentry"></a><span data-ttu-id="5cd25-103">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="5cd25-103">MSGSERVICEENTRY</span></span>

  
  
<span data-ttu-id="5cd25-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5cd25-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5cd25-105">定义以支持消息服务配置邮件服务入口点函数的原型。</span><span class="sxs-lookup"><span data-stu-id="5cd25-105">Defines a prototype for a message service entry point function to support message service configuration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5cd25-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="5cd25-106">Header file:</span></span>  <br/> |<span data-ttu-id="5cd25-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="5cd25-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="5cd25-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="5cd25-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="5cd25-109">消息服务</span><span class="sxs-lookup"><span data-stu-id="5cd25-109">Message services</span></span>  <br/> |
|<span data-ttu-id="5cd25-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="5cd25-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="5cd25-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="5cd25-111">MAPI</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="5cd25-112">参数</span><span class="sxs-lookup"><span data-stu-id="5cd25-112">Parameters</span></span>

 <span data-ttu-id="5cd25-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="5cd25-113">_hInstance_</span></span>
  
> <span data-ttu-id="5cd25-114">[in]服务 providerDLL 实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="5cd25-114">[in] Handle of the instance of the service providerDLL.</span></span> <span data-ttu-id="5cd25-115">窗口的句通常用于检索资源。</span><span class="sxs-lookup"><span data-stu-id="5cd25-115">The handle is typically used to retrieve resources.</span></span> 
    
 <span data-ttu-id="5cd25-116">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="5cd25-116">_lpMalloc_</span></span>
  
> <span data-ttu-id="5cd25-117">[in]对内存分配器对象公开的 OLE **IMalloc**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="5cd25-117">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="5cd25-118">邮件服务可能需要使用某些如**IStream**接口时使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="5cd25-118">The message service may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="5cd25-119">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="5cd25-119">_lpMAPISup_</span></span>
  
> <span data-ttu-id="5cd25-120">[in]指向[IMAPISupport: IUnknown](imapisupportiunknown.md)接口实现。</span><span class="sxs-lookup"><span data-stu-id="5cd25-120">[in] Pointer to an [IMAPISupport : IUnknown](imapisupportiunknown.md) interface implementation.</span></span> 
    
 <span data-ttu-id="5cd25-121">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="5cd25-121">_ulUIParam_</span></span>
  
> <span data-ttu-id="5cd25-122">[in]用于将用户界面的信息传递给函数或零特定于实现的值。</span><span class="sxs-lookup"><span data-stu-id="5cd25-122">[in] An implementation-specific value used for passing user interface information to a function or zero.</span></span> <span data-ttu-id="5cd25-123">_UlUIParam_参数配置对话框的父窗口句柄并且的类型为 HWND （强制转换为 ULONG_PTR）。</span><span class="sxs-lookup"><span data-stu-id="5cd25-123">The  _ulUIParam_ parameter is the parent window handle for the configuration dialog box and is of type HWND (cast to a ULONG_PTR).</span></span> <span data-ttu-id="5cd25-124">值为零表示没有父窗口。</span><span class="sxs-lookup"><span data-stu-id="5cd25-124">A value of zero indicates that there is no parent window.</span></span> 
    
 <span data-ttu-id="5cd25-125">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5cd25-125">_ulFlags_</span></span>
  
> <span data-ttu-id="5cd25-126">[in]标志指示的服务项功能的选项的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5cd25-126">[in] Bitmask of flags indicating options for the service entry function.</span></span> <span data-ttu-id="5cd25-127">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5cd25-127">The following flags can be set:</span></span>
    
<span data-ttu-id="5cd25-128">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5cd25-128">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5cd25-129">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5cd25-129">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="5cd25-130">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5cd25-130">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
<span data-ttu-id="5cd25-131">MSG_SERVICE_UI_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="5cd25-131">MSG_SERVICE_UI_READ_ONLY</span></span> 
  
> <span data-ttu-id="5cd25-132">该服务的配置用户界面应显示当前配置，但不是允许用户更改它。</span><span class="sxs-lookup"><span data-stu-id="5cd25-132">The service's configuration user interface should display the current configuration but not allow the user to change it.</span></span> 
    
<span data-ttu-id="5cd25-133">SERVICE_UI_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="5cd25-133">SERVICE_UI_ALLOWED</span></span> 
  
> <span data-ttu-id="5cd25-134">允许有必要，将显示配置对话框。</span><span class="sxs-lookup"><span data-stu-id="5cd25-134">Permits a configuration dialog box to be displayed if necessary.</span></span> <span data-ttu-id="5cd25-135">SERVICE_UI_ALLOWED 标志设置时，应显示对话框才_lpProps_属性值数组为空或不包含无效的配置。</span><span class="sxs-lookup"><span data-stu-id="5cd25-135">When the SERVICE_UI_ALLOWED flag is set, the dialog box should be displayed only if the  _lpProps_ property value array is empty or does not contain a valid configuration.</span></span> <span data-ttu-id="5cd25-136">如果未设置 SERVICE_UI_ALLOWED，如果设置了 SERVICE_UI_ALWAYS 标志，可能仍被显示对话框。</span><span class="sxs-lookup"><span data-stu-id="5cd25-136">If SERVICE_UI_ALLOWED is not set, a dialog box might still be displayed if the SERVICE_UI_ALWAYS flag is set.</span></span> 
    
<span data-ttu-id="5cd25-137">UI_CURRENT_PROVIDER_FIRST</span><span class="sxs-lookup"><span data-stu-id="5cd25-137">UI_CURRENT_PROVIDER_FIRST</span></span> 
  
> <span data-ttu-id="5cd25-138">活动的提供程序的配置对话框将显示在其他对话框顶部的请求。</span><span class="sxs-lookup"><span data-stu-id="5cd25-138">Requests that the configuration dialog box for the active provider be displayed on top of other dialog boxes.</span></span> 
    
<span data-ttu-id="5cd25-139">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="5cd25-139">SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="5cd25-140">需要邮件服务，以显示配置对话框。</span><span class="sxs-lookup"><span data-stu-id="5cd25-140">Requires the message service to display a configuration dialog box.</span></span> <span data-ttu-id="5cd25-141">如果未设置 SERVICE_UI_ALWAYS 标志，配置对话框可能仍显示如果设置了 SERVICE_UI_ALLOWED 标志和_lpProps_属性值数组中没有有效的配置信息。</span><span class="sxs-lookup"><span data-stu-id="5cd25-141">If the SERVICE_UI_ALWAYS flag is not set, a configuration dialog box might still be displayed if the SERVICE_UI_ALLOWED flag is set and valid configuration information is not available from the  _lpProps_ property value array.</span></span> <span data-ttu-id="5cd25-142">SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 必须设置为允许一个用户界面来显示。</span><span class="sxs-lookup"><span data-stu-id="5cd25-142">Either SERVICE_UI_ALLOWED or SERVICE_UI_ALWAYS must be set to allow a user interface to be displayed.</span></span> 
    
 <span data-ttu-id="5cd25-143">_ulContext_</span><span class="sxs-lookup"><span data-stu-id="5cd25-143">_ulContext_</span></span>
  
> <span data-ttu-id="5cd25-144">[in]MAPI 当前正在执行配置操作。</span><span class="sxs-lookup"><span data-stu-id="5cd25-144">[in] The configuration operation that MAPI is currently performing.</span></span> <span data-ttu-id="5cd25-145">_UlContext_参数将包含下列值之一：</span><span class="sxs-lookup"><span data-stu-id="5cd25-145">The  _ulContext_ parameter will contain one of the following values:</span></span> 
    
<span data-ttu-id="5cd25-146">MSG_SERVICE_CONFIGURE</span><span class="sxs-lookup"><span data-stu-id="5cd25-146">MSG_SERVICE_CONFIGURE</span></span> 
  
> <span data-ttu-id="5cd25-147">配置文件中应将该服务的配置更改。</span><span class="sxs-lookup"><span data-stu-id="5cd25-147">Changes to the service's configuration should be made in the profile.</span></span> <span data-ttu-id="5cd25-148">如果设置了 SERVICE_UI_ALWAYS 标志，该服务应显示其配置对话框。</span><span class="sxs-lookup"><span data-stu-id="5cd25-148">If the SERVICE_UI_ALWAYS flag is set, the service should display its configuration dialog box.</span></span> <span data-ttu-id="5cd25-149">如果设置了 SERVICE_UI_ALLOWED 标志且_lpProps_参数为空或不包含有效的配置数据，则还应显示对话框。</span><span class="sxs-lookup"><span data-stu-id="5cd25-149">The dialog box should also be displayed if the SERVICE_UI_ALLOWED flag is set and the  _lpProps_ parameter is empty or does not contain valid configuration data.</span></span> <span data-ttu-id="5cd25-150">如果_lpProps_包含有效数据，应显示没有对话框，并且该服务应使用此数据进行配置更改。</span><span class="sxs-lookup"><span data-stu-id="5cd25-150">If  _lpProps_ contains valid data, no dialog box should be displayed and the service should use this data for making the configuration change.</span></span> 
    
<span data-ttu-id="5cd25-151">MSG_SERVICE_CREATE</span><span class="sxs-lookup"><span data-stu-id="5cd25-151">MSG_SERVICE_CREATE</span></span> 
  
> <span data-ttu-id="5cd25-152">正在向一个配置文件添加服务。</span><span class="sxs-lookup"><span data-stu-id="5cd25-152">The service is being added to a profile.</span></span> <span data-ttu-id="5cd25-153">如果设置了 SERVICE_UI_ALWAYS 或 SERVICE_UI_ALLOWED 标志，该服务应显示其配置对话框。</span><span class="sxs-lookup"><span data-stu-id="5cd25-153">If either the SERVICE_UI_ALWAYS or SERVICE_UI_ALLOWED flag is set, the service should display its configuration dialog box.</span></span> <span data-ttu-id="5cd25-154">设置既标志，如果出现故障的服务。</span><span class="sxs-lookup"><span data-stu-id="5cd25-154">If neither flag is set, the service should fail.</span></span> 
    
<span data-ttu-id="5cd25-155">MSG_SERVICE_DELETE</span><span class="sxs-lookup"><span data-stu-id="5cd25-155">MSG_SERVICE_DELETE</span></span> 
  
> <span data-ttu-id="5cd25-156">正在删除服务从配置文件。</span><span class="sxs-lookup"><span data-stu-id="5cd25-156">The service is being removed from a profile.</span></span> <span data-ttu-id="5cd25-157">在接收此事件，该服务应返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="5cd25-157">After receiving this event, the service should return S_OK.</span></span>
    
<span data-ttu-id="5cd25-158">MSG_SERVICE_INSTALL</span><span class="sxs-lookup"><span data-stu-id="5cd25-158">MSG_SERVICE_INSTALL</span></span> 
  
> <span data-ttu-id="5cd25-159">该服务已从网络、 软盘或其他外部介质安装到用户的工作站。</span><span class="sxs-lookup"><span data-stu-id="5cd25-159">The service has been installed to the user's workstation from a network, floppy disk, or other external medium.</span></span> <span data-ttu-id="5cd25-160">后接收此事件，该服务通常返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="5cd25-160">After receiving this event, the service usually returns S_OK.</span></span> 
    
<span data-ttu-id="5cd25-161">MSG_SERVICE_PROVIDER_CREATE</span><span class="sxs-lookup"><span data-stu-id="5cd25-161">MSG_SERVICE_PROVIDER_CREATE</span></span> 
  
> <span data-ttu-id="5cd25-162">该服务创建提供程序的其他实例的请求。</span><span class="sxs-lookup"><span data-stu-id="5cd25-162">Requests that the service create an additional instance of a provider.</span></span> <span data-ttu-id="5cd25-163">如果服务支持此操作，它应调用[IProviderAdmin::CreateProvider](iprovideradmin-createprovider.md)。</span><span class="sxs-lookup"><span data-stu-id="5cd25-163">If the service supports this operation, it should call [IProviderAdmin::CreateProvider](iprovideradmin-createprovider.md).</span></span> <span data-ttu-id="5cd25-164">如果服务不支持此操作，它可以返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="5cd25-164">If the service does not support this operation, it can return MAPI_E_NO_SUPPORT.</span></span> 
    
<span data-ttu-id="5cd25-165">MSG_SERVICE_PROVIDER_DELETE</span><span class="sxs-lookup"><span data-stu-id="5cd25-165">MSG_SERVICE_PROVIDER_DELETE</span></span> 
  
> <span data-ttu-id="5cd25-166">服务删除提供程序实例的请求。</span><span class="sxs-lookup"><span data-stu-id="5cd25-166">Requests that the service delete a provider instance.</span></span> <span data-ttu-id="5cd25-167">如果服务支持此操作，它应调用[IProviderAdmin::DeleteProvider](iprovideradmin-deleteprovider.md)。</span><span class="sxs-lookup"><span data-stu-id="5cd25-167">If the service supports this operation, it should call [IProviderAdmin::DeleteProvider](iprovideradmin-deleteprovider.md).</span></span> <span data-ttu-id="5cd25-168">如果服务不支持此操作，它可以返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="5cd25-168">If the service does not support this operation, it can return MAPI_E_NO_SUPPORT.</span></span>
    
<span data-ttu-id="5cd25-169">MSG_SERVICE_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="5cd25-169">MSG_SERVICE_UNINSTALL</span></span> 
  
> <span data-ttu-id="5cd25-170">正在删除服务。</span><span class="sxs-lookup"><span data-stu-id="5cd25-170">The service is being removed.</span></span> <span data-ttu-id="5cd25-171">接收此事件之后, 服务可以执行之前服务结束，然后返回成功值应该执行任何清理任务。</span><span class="sxs-lookup"><span data-stu-id="5cd25-171">After receiving this event, the service can perform any cleanup tasks that should be done before the service ends and then return with a success value.</span></span> <span data-ttu-id="5cd25-172">如果用户取消删除，该服务应返回 MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="5cd25-172">If the user cancels the removal, the service should return MAPI_E_USER_CANCEL.</span></span> 
    
 <span data-ttu-id="5cd25-173">_cValues_</span><span class="sxs-lookup"><span data-stu-id="5cd25-173">_cValues_</span></span>
  
> <span data-ttu-id="5cd25-174">[in]Count 属性值数组中的指向_lpProps_参数。</span><span class="sxs-lookup"><span data-stu-id="5cd25-174">[in] Count of property values in the array pointed to by the  _lpProps_ parameter.</span></span> <span data-ttu-id="5cd25-175">_CValues_参数的值为零，如果 MAPI 没有属性值传递。</span><span class="sxs-lookup"><span data-stu-id="5cd25-175">The value of the  _cValues_ parameter is zero if MAPI is passing no property values.</span></span> 
    
 <span data-ttu-id="5cd25-176">_lpProps_</span><span class="sxs-lookup"><span data-stu-id="5cd25-176">_lpProps_</span></span>
  
> <span data-ttu-id="5cd25-177">[in]指向数组可选[SPropValue](spropvalue.md)结构指示函数将使用中配置邮件服务的提供程序支持的属性值。</span><span class="sxs-lookup"><span data-stu-id="5cd25-177">[in] Pointer to an optional array of [SPropValue](spropvalue.md) structures indicating values for provider-supported properties that the function will use in configuring the message service.</span></span> <span data-ttu-id="5cd25-178">如果_ulContext_参数设置为 MSG_SERVICE_CONFIGURE，该函数仅使用此参数。</span><span class="sxs-lookup"><span data-stu-id="5cd25-178">The function only uses this parameter if the  _ulContext_ parameter is set to MSG_SERVICE_CONFIGURE.</span></span> <span data-ttu-id="5cd25-179">此参数常用将传递给基于文件的服务，如个人通讯簿服务文件的路径。</span><span class="sxs-lookup"><span data-stu-id="5cd25-179">This parameter is commonly used to pass the path to a file for a file-based service, such as a personal address book service.</span></span> <span data-ttu-id="5cd25-180">如果不_ulFlags_参数中传递 MSG_SERVICE_CONFIGURE 标志，则_lpProps_参数必须为零。</span><span class="sxs-lookup"><span data-stu-id="5cd25-180">If the MSG_SERVICE_CONFIGURE flag is not passed in the  _ulFlags_ parameter, the  _lpProps_ parameter must be zero.</span></span> 
    
 <span data-ttu-id="5cd25-181">_lpProviderAdmin_</span><span class="sxs-lookup"><span data-stu-id="5cd25-181">_lpProviderAdmin_</span></span>
  
> <span data-ttu-id="5cd25-182">[in]指向该函数可用于为当前消息服务中的特定提供程序查找配置文件部分[IProviderAdmin:IUnknown](iprovideradminiunknown.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="5cd25-182">[in] Pointer to an [IProviderAdmin:IUnknown](iprovideradminiunknown.md) interface that the function can use to locate profile sections for a specific provider in the current message service.</span></span> 
    
 <span data-ttu-id="5cd25-183">_lppMapiError_</span><span class="sxs-lookup"><span data-stu-id="5cd25-183">_lppMapiError_</span></span>
  
> <span data-ttu-id="5cd25-184">[输出]指向[MAPIERROR](mapierror.md)结构。</span><span class="sxs-lookup"><span data-stu-id="5cd25-184">[out] Pointer to a [MAPIERROR](mapierror.md) structure.</span></span> <span data-ttu-id="5cd25-185">与[MAPIAllocateBuffer](mapiallocatebuffer.md)函数分配结构。</span><span class="sxs-lookup"><span data-stu-id="5cd25-185">The structure is allocated with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> <span data-ttu-id="5cd25-186">所有成员都是可选的尽管大多数结构将有效的错误消息中包含字符串_lpszError_成员。</span><span class="sxs-lookup"><span data-stu-id="5cd25-186">All members are optional, although most structures will contain a valid error message string in the  _lpszError_ member.</span></span> <span data-ttu-id="5cd25-187">是否存在_lpszComponent_或_lpszError_结构的成员，必须最终到[MAPIFreeBuffer](mapifreebuffer.md)的基本结构上一次调用释放其内存。</span><span class="sxs-lookup"><span data-stu-id="5cd25-187">If the  _lpszComponent_ or  _lpszError_ members of the structure are present, their memory must eventually be freed by a single call to [MAPIFreeBuffer](mapifreebuffer.md) on the base structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5cd25-188">返回值</span><span class="sxs-lookup"><span data-stu-id="5cd25-188">Return value</span></span>

<span data-ttu-id="5cd25-189">S_OK</span><span class="sxs-lookup"><span data-stu-id="5cd25-189">S_OK</span></span> 
  
> <span data-ttu-id="5cd25-190">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="5cd25-190">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="5cd25-191">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="5cd25-191">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="5cd25-192">尚未配置服务提供商。</span><span class="sxs-lookup"><span data-stu-id="5cd25-192">The service provider has not been configured.</span></span> 
    
<span data-ttu-id="5cd25-193">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="5cd25-193">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="5cd25-194">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="5cd25-194">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
<span data-ttu-id="5cd25-195">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="5cd25-195">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="5cd25-196">提供程序不支持对其对象的更改，或不支持的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="5cd25-196">The provider either does not support changes to its objects or does not support notification of changes.</span></span> 
    
<span data-ttu-id="5cd25-197">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="5cd25-197">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="5cd25-198">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="5cd25-198">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation only supports Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5cd25-199">注解</span><span class="sxs-lookup"><span data-stu-id="5cd25-199">Remarks</span></span>

<span data-ttu-id="5cd25-200">使用**MSGSERVICEENTRY**函数原型定义的函数启用消息服务来配置自己或执行其他特定于服务的操作。</span><span class="sxs-lookup"><span data-stu-id="5cd25-200">A function defined using the **MSGSERVICEENTRY** function prototype enables message services to configure themselves or to perform other service-specific actions.</span></span> <span data-ttu-id="5cd25-201">该函数主要提供一个对话框，在其中用户可以向消息服务更改特定的设置。</span><span class="sxs-lookup"><span data-stu-id="5cd25-201">The function primarily furnishes a dialog box in which the user can change settings specific to the message service.</span></span> <span data-ttu-id="5cd25-202">它还可以使用_lpProps_参数中传递的属性值数组支持编程配置。</span><span class="sxs-lookup"><span data-stu-id="5cd25-202">It can also support programmatic configuration by using the property value array passed in the  _lpProps_ parameter.</span></span> <span data-ttu-id="5cd25-203">除非服务支持配置文件向导中，需要它的编程配置是可选的。</span><span class="sxs-lookup"><span data-stu-id="5cd25-203">Programmatic configuration is optional unless the service supports the Profile Wizard, for which it is required.</span></span> 
  
<span data-ttu-id="5cd25-204">MAPI 从控制面板应用程序或向客户端应用程序调用[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)或[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)响应中调用此入口点。</span><span class="sxs-lookup"><span data-stu-id="5cd25-204">MAPI calls this entry point from the Control Panel application or in response to a client application calling [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) or [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md).</span></span> 
  
<span data-ttu-id="5cd25-205">MAPI 将函数名的消息服务使用**MSGSERVICEENTRY**原型，但首选名称**ServiceEntry**置于没有限制。</span><span class="sxs-lookup"><span data-stu-id="5cd25-205">MAPI places no restriction on the function name that a message service uses for the **MSGSERVICEENTRY** prototype but prefers the name **ServiceEntry**.</span></span> <span data-ttu-id="5cd25-206">没有任何限制上的第几个函数，并且单个提供程序 DLL 可以包含多个函数。</span><span class="sxs-lookup"><span data-stu-id="5cd25-206">There is no restriction on the ordinal for the function, and a single provider DLL can contain more than one function.</span></span> <span data-ttu-id="5cd25-207">但是，仅之一功能可以进行命名**ServiceEntry**。</span><span class="sxs-lookup"><span data-stu-id="5cd25-207">However, only one of the functions can be named **ServiceEntry**.</span></span> 
  
<span data-ttu-id="5cd25-208">消息服务可以使用[BuildDisplayTable](builddisplaytable.md)函数和[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)方法简化配置对话框框实施。</span><span class="sxs-lookup"><span data-stu-id="5cd25-208">A message service can use the [BuildDisplayTable](builddisplaytable.md) function and the [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method to simplify configuration dialog box implementation.</span></span> 
  
<span data-ttu-id="5cd25-209">有可能，用户可以取消 MSG_SERVICE_UNINSTALL 操作。</span><span class="sxs-lookup"><span data-stu-id="5cd25-209">It is possible for a user to cancel a MSG_SERVICE_UNINSTALL operation.</span></span> <span data-ttu-id="5cd25-210">在这种情况下， **ServiceEntry**函数应检查以验证该服务不会删除，并返回 MAPI_E_USER_CANCEL，如果服务保持已安装的用户。</span><span class="sxs-lookup"><span data-stu-id="5cd25-210">In this case, the **ServiceEntry** function should check with the user to verify that the service should not be removed and return MAPI_E_USER_CANCEL if the service remains installed.</span></span> 
  
<span data-ttu-id="5cd25-211">基于**MSGSERVICEENTRY**原型函数返回列出的 HRESULT 值之一。</span><span class="sxs-lookup"><span data-stu-id="5cd25-211">A function based on the **MSGSERVICEENTRY** prototype returns one of the HRESULT values listed.</span></span> <span data-ttu-id="5cd25-212">MAPI 客户端的呼叫[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)响应时转发此值。</span><span class="sxs-lookup"><span data-stu-id="5cd25-212">MAPI forwards this value when responding to a client's call to [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md).</span></span> 
  
<span data-ttu-id="5cd25-213">导出服务条目函数的消息服务必须消息服务的一节中包括的**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 和**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 属性MAPISVC.INF。</span><span class="sxs-lookup"><span data-stu-id="5cd25-213">Message services that export a service entry function must include the **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) and **PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) properties in the message service section of MAPISVC.INF.</span></span> 
  

