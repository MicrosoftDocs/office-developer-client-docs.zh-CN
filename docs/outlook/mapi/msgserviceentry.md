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
# <a name="msgserviceentry"></a><span data-ttu-id="66065-103">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="66065-103">MSGSERVICEENTRY</span></span>

  
  
<span data-ttu-id="66065-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="66065-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="66065-105">定义邮件服务入口点函数的原型以支持邮件服务配置。</span><span class="sxs-lookup"><span data-stu-id="66065-105">Defines a prototype for a message service entry point function to support message service configuration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="66065-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="66065-106">Header file:</span></span>  <br/> |<span data-ttu-id="66065-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="66065-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="66065-108">定义的函数实现方：</span><span class="sxs-lookup"><span data-stu-id="66065-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="66065-109">邮件服务</span><span class="sxs-lookup"><span data-stu-id="66065-109">Message services</span></span>  <br/> |
|<span data-ttu-id="66065-110">由调用的已定义函数：</span><span class="sxs-lookup"><span data-stu-id="66065-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="66065-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="66065-111">MAPI</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="66065-112">参数</span><span class="sxs-lookup"><span data-stu-id="66065-112">Parameters</span></span>

 <span data-ttu-id="66065-113">_hInstance_</span><span class="sxs-lookup"><span data-stu-id="66065-113">_hInstance_</span></span>
  
> <span data-ttu-id="66065-114">[in]服务提供程序DLL 实例的句柄。</span><span class="sxs-lookup"><span data-stu-id="66065-114">[in] Handle of the instance of the service providerDLL.</span></span> <span data-ttu-id="66065-115">句柄通常用于检索资源。</span><span class="sxs-lookup"><span data-stu-id="66065-115">The handle is typically used to retrieve resources.</span></span> 
    
 <span data-ttu-id="66065-116">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="66065-116">_lpMalloc_</span></span>
  
> <span data-ttu-id="66065-117">[in]指向公开 OLE **IMalloc 接口的内存分配器对象的** 指针。</span><span class="sxs-lookup"><span data-stu-id="66065-117">[in] Pointer to a memory allocator object exposing the OLE **IMalloc** interface.</span></span> <span data-ttu-id="66065-118">使用某些接口（如 **IStream）** 时，邮件服务可能需要使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="66065-118">The message service may need to use this allocation method when working with certain interfaces such as **IStream**.</span></span> 
    
 <span data-ttu-id="66065-119">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="66065-119">_lpMAPISup_</span></span>
  
> <span data-ttu-id="66065-120">[in]指向 [IMAPISupport ： IUnknown](imapisupportiunknown.md) 接口实现指针。</span><span class="sxs-lookup"><span data-stu-id="66065-120">[in] Pointer to an [IMAPISupport : IUnknown](imapisupportiunknown.md) interface implementation.</span></span> 
    
 <span data-ttu-id="66065-121">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="66065-121">_ulUIParam_</span></span>
  
> <span data-ttu-id="66065-122">[in]用于将用户界面信息传递给函数或零的特定于实现的值。</span><span class="sxs-lookup"><span data-stu-id="66065-122">[in] An implementation-specific value used for passing user interface information to a function or zero.</span></span> <span data-ttu-id="66065-123">_ulUIParam_ 参数是配置对话框的父窗口句柄，其类型为 HWND (强制转换到ULONG_PTR) 。</span><span class="sxs-lookup"><span data-stu-id="66065-123">The  _ulUIParam_ parameter is the parent window handle for the configuration dialog box and is of type HWND (cast to a ULONG_PTR).</span></span> <span data-ttu-id="66065-124">值为零表示没有父窗口。</span><span class="sxs-lookup"><span data-stu-id="66065-124">A value of zero indicates that there is no parent window.</span></span> 
    
 <span data-ttu-id="66065-125">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="66065-125">_ulFlags_</span></span>
  
> <span data-ttu-id="66065-126">[in]指示服务输入函数选项的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="66065-126">[in] Bitmask of flags indicating options for the service entry function.</span></span> <span data-ttu-id="66065-127">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="66065-127">The following flags can be set:</span></span>
    
<span data-ttu-id="66065-128">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="66065-128">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="66065-129">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="66065-129">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="66065-130">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="66065-130">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
<span data-ttu-id="66065-131">MSG_SERVICE_UI_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="66065-131">MSG_SERVICE_UI_READ_ONLY</span></span> 
  
> <span data-ttu-id="66065-132">服务的配置用户界面应显示当前配置，但不允许用户更改它。</span><span class="sxs-lookup"><span data-stu-id="66065-132">The service's configuration user interface should display the current configuration but not allow the user to change it.</span></span> 
    
<span data-ttu-id="66065-133">SERVICE_UI_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="66065-133">SERVICE_UI_ALLOWED</span></span> 
  
> <span data-ttu-id="66065-134">允许显示配置对话框（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="66065-134">Permits a configuration dialog box to be displayed if necessary.</span></span> <span data-ttu-id="66065-135">设置 SERVICE_UI_ALLOWED 标志时，对话框应仅在  _lpProps_ 属性值数组为空或不包含有效配置时显示。</span><span class="sxs-lookup"><span data-stu-id="66065-135">When the SERVICE_UI_ALLOWED flag is set, the dialog box should be displayed only if the  _lpProps_ property value array is empty or does not contain a valid configuration.</span></span> <span data-ttu-id="66065-136">如果未SERVICE_UI_ALLOWED，则设置该对话框时，SERVICE_UI_ALWAYS显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="66065-136">If SERVICE_UI_ALLOWED is not set, a dialog box might still be displayed if the SERVICE_UI_ALWAYS flag is set.</span></span> 
    
<span data-ttu-id="66065-137">UI_CURRENT_PROVIDER_FIRST</span><span class="sxs-lookup"><span data-stu-id="66065-137">UI_CURRENT_PROVIDER_FIRST</span></span> 
  
> <span data-ttu-id="66065-138">请求将活动提供程序的配置对话框显示在其他对话框的顶部。</span><span class="sxs-lookup"><span data-stu-id="66065-138">Requests that the configuration dialog box for the active provider be displayed on top of other dialog boxes.</span></span> 
    
<span data-ttu-id="66065-139">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="66065-139">SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="66065-140">需要邮件服务显示配置对话框。</span><span class="sxs-lookup"><span data-stu-id="66065-140">Requires the message service to display a configuration dialog box.</span></span> <span data-ttu-id="66065-141">如果未SERVICE_UI_ALWAYS，如果设置了 SERVICE_UI_ALLOWED 标志，并且  _lpProps_ 属性值数组中未提供有效的配置信息，则仍可能会显示配置对话框。</span><span class="sxs-lookup"><span data-stu-id="66065-141">If the SERVICE_UI_ALWAYS flag is not set, a configuration dialog box might still be displayed if the SERVICE_UI_ALLOWED flag is set and valid configuration information is not available from the  _lpProps_ property value array.</span></span> <span data-ttu-id="66065-142">必须SERVICE_UI_ALLOWED或SERVICE_UI_ALWAYS用户界面，以允许显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="66065-142">Either SERVICE_UI_ALLOWED or SERVICE_UI_ALWAYS must be set to allow a user interface to be displayed.</span></span> 
    
 <span data-ttu-id="66065-143">_ulContext_</span><span class="sxs-lookup"><span data-stu-id="66065-143">_ulContext_</span></span>
  
> <span data-ttu-id="66065-144">[in]MAPI 当前正在执行的配置操作。</span><span class="sxs-lookup"><span data-stu-id="66065-144">[in] The configuration operation that MAPI is currently performing.</span></span> <span data-ttu-id="66065-145">_ulContext_ 参数将包含下列值之一：</span><span class="sxs-lookup"><span data-stu-id="66065-145">The  _ulContext_ parameter will contain one of the following values:</span></span> 
    
<span data-ttu-id="66065-146">MSG_SERVICE_CONFIGURE</span><span class="sxs-lookup"><span data-stu-id="66065-146">MSG_SERVICE_CONFIGURE</span></span> 
  
> <span data-ttu-id="66065-147">应在配置文件中更改服务的配置。</span><span class="sxs-lookup"><span data-stu-id="66065-147">Changes to the service's configuration should be made in the profile.</span></span> <span data-ttu-id="66065-148">如果SERVICE_UI_ALWAYS，服务应显示其配置对话框。</span><span class="sxs-lookup"><span data-stu-id="66065-148">If the SERVICE_UI_ALWAYS flag is set, the service should display its configuration dialog box.</span></span> <span data-ttu-id="66065-149">如果设置了 lpProps 参数，SERVICE_UI_ALLOWED  _lpProps_ 参数为空或不包含有效的配置数据，则还应显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="66065-149">The dialog box should also be displayed if the SERVICE_UI_ALLOWED flag is set and the  _lpProps_ parameter is empty or does not contain valid configuration data.</span></span> <span data-ttu-id="66065-150">如果  _lpProps_ 包含有效数据，则不应显示任何对话框，服务应该使用此数据进行配置更改。</span><span class="sxs-lookup"><span data-stu-id="66065-150">If  _lpProps_ contains valid data, no dialog box should be displayed and the service should use this data for making the configuration change.</span></span> 
    
<span data-ttu-id="66065-151">MSG_SERVICE_CREATE</span><span class="sxs-lookup"><span data-stu-id="66065-151">MSG_SERVICE_CREATE</span></span> 
  
> <span data-ttu-id="66065-152">服务将添加到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="66065-152">The service is being added to a profile.</span></span> <span data-ttu-id="66065-153">如果设置了 SERVICE_UI_ALWAYS 或 SERVICE_UI_ALLOWED 标志，则服务应显示其配置对话框。</span><span class="sxs-lookup"><span data-stu-id="66065-153">If either the SERVICE_UI_ALWAYS or SERVICE_UI_ALLOWED flag is set, the service should display its configuration dialog box.</span></span> <span data-ttu-id="66065-154">如果未设置任何标志，则服务应失败。</span><span class="sxs-lookup"><span data-stu-id="66065-154">If neither flag is set, the service should fail.</span></span> 
    
<span data-ttu-id="66065-155">MSG_SERVICE_DELETE</span><span class="sxs-lookup"><span data-stu-id="66065-155">MSG_SERVICE_DELETE</span></span> 
  
> <span data-ttu-id="66065-156">服务正在从配置文件中删除。</span><span class="sxs-lookup"><span data-stu-id="66065-156">The service is being removed from a profile.</span></span> <span data-ttu-id="66065-157">收到此事件后，服务应返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="66065-157">After receiving this event, the service should return S_OK.</span></span>
    
<span data-ttu-id="66065-158">MSG_SERVICE_INSTALL</span><span class="sxs-lookup"><span data-stu-id="66065-158">MSG_SERVICE_INSTALL</span></span> 
  
> <span data-ttu-id="66065-159">服务已从网络、软盘或其他外部介质安装到用户的工作站。</span><span class="sxs-lookup"><span data-stu-id="66065-159">The service has been installed to the user's workstation from a network, floppy disk, or other external medium.</span></span> <span data-ttu-id="66065-160">收到此事件后，该服务通常会返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="66065-160">After receiving this event, the service usually returns S_OK.</span></span> 
    
<span data-ttu-id="66065-161">MSG_SERVICE_PROVIDER_CREATE</span><span class="sxs-lookup"><span data-stu-id="66065-161">MSG_SERVICE_PROVIDER_CREATE</span></span> 
  
> <span data-ttu-id="66065-162">请求服务创建提供程序的其他实例。</span><span class="sxs-lookup"><span data-stu-id="66065-162">Requests that the service create an additional instance of a provider.</span></span> <span data-ttu-id="66065-163">如果服务支持此操作，则它应调用 [IProviderAdmin：：CreateProvider](iprovideradmin-createprovider.md)。</span><span class="sxs-lookup"><span data-stu-id="66065-163">If the service supports this operation, it should call [IProviderAdmin::CreateProvider](iprovideradmin-createprovider.md).</span></span> <span data-ttu-id="66065-164">如果服务不支持此操作，则它会返回MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="66065-164">If the service does not support this operation, it can return MAPI_E_NO_SUPPORT.</span></span> 
    
<span data-ttu-id="66065-165">MSG_SERVICE_PROVIDER_DELETE</span><span class="sxs-lookup"><span data-stu-id="66065-165">MSG_SERVICE_PROVIDER_DELETE</span></span> 
  
> <span data-ttu-id="66065-166">请求服务删除提供程序实例。</span><span class="sxs-lookup"><span data-stu-id="66065-166">Requests that the service delete a provider instance.</span></span> <span data-ttu-id="66065-167">如果服务支持此操作，则它应调用 [IProviderAdmin：:D eleteProvider](iprovideradmin-deleteprovider.md)。</span><span class="sxs-lookup"><span data-stu-id="66065-167">If the service supports this operation, it should call [IProviderAdmin::DeleteProvider](iprovideradmin-deleteprovider.md).</span></span> <span data-ttu-id="66065-168">如果服务不支持此操作，则它会返回MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="66065-168">If the service does not support this operation, it can return MAPI_E_NO_SUPPORT.</span></span>
    
<span data-ttu-id="66065-169">MSG_SERVICE_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="66065-169">MSG_SERVICE_UNINSTALL</span></span> 
  
> <span data-ttu-id="66065-170">服务正在删除。</span><span class="sxs-lookup"><span data-stu-id="66065-170">The service is being removed.</span></span> <span data-ttu-id="66065-171">收到此事件后，该服务可以执行应在服务结束之前完成的任何清理任务，然后返回一个成功值。</span><span class="sxs-lookup"><span data-stu-id="66065-171">After receiving this event, the service can perform any cleanup tasks that should be done before the service ends and then return with a success value.</span></span> <span data-ttu-id="66065-172">如果用户取消删除，服务应返回MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="66065-172">If the user cancels the removal, the service should return MAPI_E_USER_CANCEL.</span></span> 
    
 <span data-ttu-id="66065-173">_cValues_</span><span class="sxs-lookup"><span data-stu-id="66065-173">_cValues_</span></span>
  
> <span data-ttu-id="66065-174">[in]  _lpProps_ 参数指向的数组中的属性值计数。</span><span class="sxs-lookup"><span data-stu-id="66065-174">[in] Count of property values in the array pointed to by the  _lpProps_ parameter.</span></span> <span data-ttu-id="66065-175">如果 MAPI 未传递任何属性值，  _则 cValues_ 参数的值为零。</span><span class="sxs-lookup"><span data-stu-id="66065-175">The value of the  _cValues_ parameter is zero if MAPI is passing no property values.</span></span> 
    
 <span data-ttu-id="66065-176">_lpProps_</span><span class="sxs-lookup"><span data-stu-id="66065-176">_lpProps_</span></span>
  
> <span data-ttu-id="66065-177">[in]指向 [SPropValue](spropvalue.md) 结构的可选数组的指针，指示函数将在配置邮件服务时使用的提供程序支持属性的值。</span><span class="sxs-lookup"><span data-stu-id="66065-177">[in] Pointer to an optional array of [SPropValue](spropvalue.md) structures indicating values for provider-supported properties that the function will use in configuring the message service.</span></span> <span data-ttu-id="66065-178">如果  _ulContext_ 参数设置为 MSG_SERVICE_CONFIGURE。</span><span class="sxs-lookup"><span data-stu-id="66065-178">The function only uses this parameter if the  _ulContext_ parameter is set to MSG_SERVICE_CONFIGURE.</span></span> <span data-ttu-id="66065-179">此参数通常用于传递基于文件的服务（如个人通讯簿服务）的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="66065-179">This parameter is commonly used to pass the path to a file for a file-based service, such as a personal address book service.</span></span> <span data-ttu-id="66065-180">如果未在  _ulFlags_ 参数中传递 MSG_SERVICE_CONFIGURE 标志，则  _lpProps_ 参数必须为零。</span><span class="sxs-lookup"><span data-stu-id="66065-180">If the MSG_SERVICE_CONFIGURE flag is not passed in the  _ulFlags_ parameter, the  _lpProps_ parameter must be zero.</span></span> 
    
 <span data-ttu-id="66065-181">_lpProviderAdmin_</span><span class="sxs-lookup"><span data-stu-id="66065-181">_lpProviderAdmin_</span></span>
  
> <span data-ttu-id="66065-182">[in]指向 [IProviderAdmin：IUnknown](iprovideradminiunknown.md) 接口的指针，该接口可用于在当前邮件服务中查找特定提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="66065-182">[in] Pointer to an [IProviderAdmin:IUnknown](iprovideradminiunknown.md) interface that the function can use to locate profile sections for a specific provider in the current message service.</span></span> 
    
 <span data-ttu-id="66065-183">_lppMapiError_</span><span class="sxs-lookup"><span data-stu-id="66065-183">_lppMapiError_</span></span>
  
> <span data-ttu-id="66065-184">[out]指向 [MAPIERROR 结构的](mapierror.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="66065-184">[out] Pointer to a [MAPIERROR](mapierror.md) structure.</span></span> <span data-ttu-id="66065-185">该结构通过 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数进行分配。</span><span class="sxs-lookup"><span data-stu-id="66065-185">The structure is allocated with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> <span data-ttu-id="66065-186">虽然大多数结构将在  _lpszError_ 成员中包含有效的错误消息字符串，但所有成员都是可选的。</span><span class="sxs-lookup"><span data-stu-id="66065-186">All members are optional, although most structures will contain a valid error message string in the  _lpszError_ member.</span></span> <span data-ttu-id="66065-187">如果存在  _结构的 lpszComponent_ 或  _lpszError_ 成员，最终必须通过对基本结构上的 [MAPIFreeBuffer](mapifreebuffer.md) 的单个调用释放其内存。</span><span class="sxs-lookup"><span data-stu-id="66065-187">If the  _lpszComponent_ or  _lpszError_ members of the structure are present, their memory must eventually be freed by a single call to [MAPIFreeBuffer](mapifreebuffer.md) on the base structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="66065-188">返回值</span><span class="sxs-lookup"><span data-stu-id="66065-188">Return value</span></span>

<span data-ttu-id="66065-189">S_OK</span><span class="sxs-lookup"><span data-stu-id="66065-189">S_OK</span></span> 
  
> <span data-ttu-id="66065-190">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="66065-190">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="66065-191">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="66065-191">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="66065-192">尚未配置服务提供商。</span><span class="sxs-lookup"><span data-stu-id="66065-192">The service provider has not been configured.</span></span> 
    
<span data-ttu-id="66065-193">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="66065-193">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="66065-194">用户通常通过单击对话框中的"取消" **按钮来取消** 操作。</span><span class="sxs-lookup"><span data-stu-id="66065-194">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
<span data-ttu-id="66065-195">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="66065-195">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="66065-196">提供程序不支持更改其对象，或者不支持更改通知。</span><span class="sxs-lookup"><span data-stu-id="66065-196">The provider either does not support changes to its objects or does not support notification of changes.</span></span> 
    
<span data-ttu-id="66065-197">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="66065-197">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="66065-198">设置 MAPI_UNICODE 标志，并且实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="66065-198">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation only supports Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="66065-199">备注</span><span class="sxs-lookup"><span data-stu-id="66065-199">Remarks</span></span>

<span data-ttu-id="66065-200">使用 **MSGSERVICEENTRY** 函数原型定义的函数使邮件服务可以配置自身或执行其他特定于服务的操作。</span><span class="sxs-lookup"><span data-stu-id="66065-200">A function defined using the **MSGSERVICEENTRY** function prototype enables message services to configure themselves or to perform other service-specific actions.</span></span> <span data-ttu-id="66065-201">函数主要提供一个对话框，用户可以在对话框中更改特定于邮件服务的设置。</span><span class="sxs-lookup"><span data-stu-id="66065-201">The function primarily furnishes a dialog box in which the user can change settings specific to the message service.</span></span> <span data-ttu-id="66065-202">它还可以使用传入  _lpProps_ 参数的属性值数组来支持编程配置。</span><span class="sxs-lookup"><span data-stu-id="66065-202">It can also support programmatic configuration by using the property value array passed in the  _lpProps_ parameter.</span></span> <span data-ttu-id="66065-203">编程配置是可选的，除非该服务支持配置文件向导，而该向导是必需的。</span><span class="sxs-lookup"><span data-stu-id="66065-203">Programmatic configuration is optional unless the service supports the Profile Wizard, for which it is required.</span></span> 
  
<span data-ttu-id="66065-204">MAPI 从控制面板应用程序或响应调用 [IMsgServiceAdmin：：CreateMsgService](imsgserviceadmin-createmsgservice.md) 或 [IMsgServiceAdmin：：ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)的客户端应用程序调用此入口点。</span><span class="sxs-lookup"><span data-stu-id="66065-204">MAPI calls this entry point from the Control Panel application or in response to a client application calling [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) or [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md).</span></span> 
  
<span data-ttu-id="66065-205">MAPI 对邮件服务用于 **MSGSERVICEENTRY** 原型的函数名称没有限制，但首选名称 **ServiceEntry**。</span><span class="sxs-lookup"><span data-stu-id="66065-205">MAPI places no restriction on the function name that a message service uses for the **MSGSERVICEENTRY** prototype but prefers the name **ServiceEntry**.</span></span> <span data-ttu-id="66065-206">对函数的序号没有限制，并且单个提供程序 DLL 可以包含多个函数。</span><span class="sxs-lookup"><span data-stu-id="66065-206">There is no restriction on the ordinal for the function, and a single provider DLL can contain more than one function.</span></span> <span data-ttu-id="66065-207">但是，只能将其中一个函数命名为 **ServiceEntry**。</span><span class="sxs-lookup"><span data-stu-id="66065-207">However, only one of the functions can be named **ServiceEntry**.</span></span> 
  
<span data-ttu-id="66065-208">邮件服务可以使用 [BuildDisplayTable](builddisplaytable.md) 函数和 [IMAPISupport：:D oConfigPropsheet](imapisupport-doconfigpropsheet.md) 方法来简化配置对话框实现。</span><span class="sxs-lookup"><span data-stu-id="66065-208">A message service can use the [BuildDisplayTable](builddisplaytable.md) function and the [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method to simplify configuration dialog box implementation.</span></span> 
  
<span data-ttu-id="66065-209">用户可以取消一个MSG_SERVICE_UNINSTALL操作。</span><span class="sxs-lookup"><span data-stu-id="66065-209">It is possible for a user to cancel a MSG_SERVICE_UNINSTALL operation.</span></span> <span data-ttu-id="66065-210">在这种情况下 **，ServiceEntry** 函数应检查用户以确认不应删除该服务，并返回MAPI_E_USER_CANCEL服务是否仍已安装。</span><span class="sxs-lookup"><span data-stu-id="66065-210">In this case, the **ServiceEntry** function should check with the user to verify that the service should not be removed and return MAPI_E_USER_CANCEL if the service remains installed.</span></span> 
  
<span data-ttu-id="66065-211">基于 **MSGSERVICEENTRY** 原型的函数返回列出的 HRESULT 值之一。</span><span class="sxs-lookup"><span data-stu-id="66065-211">A function based on the **MSGSERVICEENTRY** prototype returns one of the HRESULT values listed.</span></span> <span data-ttu-id="66065-212">MAPI 在响应客户端对 [IMsgServiceAdmin：：ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)的调用时转发此值。</span><span class="sxs-lookup"><span data-stu-id="66065-212">MAPI forwards this value when responding to a client's call to [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md).</span></span> 
  
<span data-ttu-id="66065-213">导出服务条目功能的邮件服务必须包括 MAPISVC.INF 的邮件服务部分中的 **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 和 **PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="66065-213">Message services that export a service entry function must include the **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) and **PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) properties in the message service section of MAPISVC.INF.</span></span> 
  

