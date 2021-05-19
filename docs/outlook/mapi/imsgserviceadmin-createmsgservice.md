---
title: IMsgServiceAdminCreateMsgService
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.CreateMsgService
api_type:
- COM
ms.assetid: 0135f049-0311-45e5-9685-78597d599a4e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e7d30c1aba8ddc1419045c1caa8524f7d2063dc5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434975"
---
# <a name="imsgserviceadmincreatemsgservice"></a><span data-ttu-id="31ae3-103">IMsgServiceAdmin::CreateMsgService</span><span class="sxs-lookup"><span data-stu-id="31ae3-103">IMsgServiceAdmin::CreateMsgService</span></span>

  
  
<span data-ttu-id="31ae3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="31ae3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="31ae3-105">已弃用：建议使用[IMsgServiceAdmin2：：CreateMsgServiceEx。](imsgserviceadmin2-createmsgserviceex.md)</span><span class="sxs-lookup"><span data-stu-id="31ae3-105">Deprecated: The use of [IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md) is recommended.</span></span> <span data-ttu-id="31ae3-106">向当前配置文件添加邮件服务。</span><span class="sxs-lookup"><span data-stu-id="31ae3-106">Adds a message service to the current profile.</span></span> 
  
```cpp
HRESULT CreateMsgService(
  LPSTR lpszService,
  LPSTR lpszDisplayName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags    
);
```

## <a name="parameters"></a><span data-ttu-id="31ae3-107">参数</span><span class="sxs-lookup"><span data-stu-id="31ae3-107">Parameters</span></span>

 <span data-ttu-id="31ae3-108">_lpszService_</span><span class="sxs-lookup"><span data-stu-id="31ae3-108">_lpszService_</span></span>
  
> <span data-ttu-id="31ae3-109">[in]指向要添加的邮件服务的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="31ae3-109">[in] A pointer to the name of the message service to add.</span></span> <span data-ttu-id="31ae3-110">此消息服务名称必须出现在 MapiSvc.inf 文件的 **[Services]** 部分中。</span><span class="sxs-lookup"><span data-stu-id="31ae3-110">This message service name must appear in the **[Services]** section of the MapiSvc.inf file.</span></span> 
    
 <span data-ttu-id="31ae3-111">_lpszDisplayName_</span><span class="sxs-lookup"><span data-stu-id="31ae3-111">_lpszDisplayName_</span></span>
  
> <span data-ttu-id="31ae3-112">[in]指向要显示名称的消息服务对象的指针。</span><span class="sxs-lookup"><span data-stu-id="31ae3-112">[in] A pointer to the display name of the message service to add.</span></span> <span data-ttu-id="31ae3-113">如果邮件服务在 MapiSvc.inf 文件中设置了 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性，则 _忽略 lpszDisplayName_ 参数。</span><span class="sxs-lookup"><span data-stu-id="31ae3-113">The  _lpszDisplayName_ parameter is ignored if the message service has set the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property in the MapiSvc.inf file.</span></span>
    
 <span data-ttu-id="31ae3-114">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="31ae3-114">_ulUIParam_</span></span>
  
> <span data-ttu-id="31ae3-115">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="31ae3-115">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span>
    
 <span data-ttu-id="31ae3-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="31ae3-116">_ulFlags_</span></span>
  
> <span data-ttu-id="31ae3-117">[in]控制邮件服务的安装方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="31ae3-117">[in] A bitmask of flags that controls how the message service is installed.</span></span> <span data-ttu-id="31ae3-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="31ae3-118">The following flags can be set:</span></span>
    
<span data-ttu-id="31ae3-119">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="31ae3-119">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="31ae3-120">lpszService 和 lpszDisplayName 参数应转换为 LPWSTR，并解释为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="31ae3-120">The lpszService and the lpszDisplayName parameters should be cast to LPWSTR and interpreted as Unicode strings.</span></span>
    
<span data-ttu-id="31ae3-121">SERVICE_NO_RESTART_WARNING</span><span class="sxs-lookup"><span data-stu-id="31ae3-121">SERVICE_NO_RESTART_WARNING</span></span>
  
> <span data-ttu-id="31ae3-122">向配置文件添加新邮件服务时，MAPI 子系统根据各种情形和条件通常确定此操作需要重新启动Outlook。</span><span class="sxs-lookup"><span data-stu-id="31ae3-122">When adding a new message service to the profile, the MAPI subsystem, based on various circumstances and criteria, often determines that this action requires a restart of Outlook.</span></span> <span data-ttu-id="31ae3-123">如果未包括 SERVICE_NO_RESTART_WARNING 标志，并且允许 UI（基于 SERVICE_UI_ALWAYS 和 SERVICE_UI_ALLOWED 标志）并且至少有一个进程已登录到当前配置文件，则此函数将显示消息"必须重新启动 Outlook，这些更改才能生效"。</span><span class="sxs-lookup"><span data-stu-id="31ae3-123">If the SERVICE_NO_RESTART_WARNING flag is not included and UI is allowed - based on the SERVICE_UI_ALWAYS and SERVICE_UI_ALLOWED flags - and at least one process is logged onto the current profile, this function displays the message "You must restart Outlook for these changes to take effect."</span></span> <span data-ttu-id="31ae3-124">包括 SERVICE_NO_RESTART_WARNING 标志将禁止显示该警告消息。</span><span class="sxs-lookup"><span data-stu-id="31ae3-124">Including the SERVICE_NO_RESTART_WARNING flag suppresses the display of that warning message.</span></span>
    
<span data-ttu-id="31ae3-125">SERVICE_UI_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="31ae3-125">SERVICE_UI_ALLOWED</span></span>
  
> <span data-ttu-id="31ae3-126">如果需要，允许使用邮件服务配置 UI。</span><span class="sxs-lookup"><span data-stu-id="31ae3-126">The message service configuration UI is allowed if needed.</span></span>
    
<span data-ttu-id="31ae3-127">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="31ae3-127">SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="31ae3-128">邮件服务显示其配置属性表。</span><span class="sxs-lookup"><span data-stu-id="31ae3-128">The message service displays its configuration property sheet.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="31ae3-129">返回值</span><span class="sxs-lookup"><span data-stu-id="31ae3-129">Return value</span></span>

<span data-ttu-id="31ae3-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="31ae3-130">S_OK</span></span> 
  
> <span data-ttu-id="31ae3-131">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="31ae3-131">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="31ae3-132">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="31ae3-132">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="31ae3-133">邮件服务名称不在 MapiSvc.inf **的 [Services]** 部分中。</span><span class="sxs-lookup"><span data-stu-id="31ae3-133">The message service name is not in the **[Services]** section of MapiSvc.inf.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="31ae3-134">备注</span><span class="sxs-lookup"><span data-stu-id="31ae3-134">Remarks</span></span>

<span data-ttu-id="31ae3-135">**IMsgServiceAdmin：：CreateMsgService** 方法将邮件服务添加到当前配置文件。</span><span class="sxs-lookup"><span data-stu-id="31ae3-135">The **IMsgServiceAdmin::CreateMsgService** method adds a message service to the current profile.</span></span> <span data-ttu-id="31ae3-136">**CreateMsgService** 调用邮件服务的入口点函数来执行任何特定于服务的配置任务。</span><span class="sxs-lookup"><span data-stu-id="31ae3-136">**CreateMsgService** calls the message service's entry point function to perform any service-specific configuration tasks.</span></span> <span data-ttu-id="31ae3-137">如果在  _ulFlags_ 参数中设置了 SERVICE_UI_ALLOWED 标志，则所安装的邮件服务可以显示属性表，以便用户能够配置其设置。</span><span class="sxs-lookup"><span data-stu-id="31ae3-137">If the SERVICE_UI_ALLOWED flag is set in the  _ulFlags_ parameter, the message service being installed can display a property sheet to enable the user to configure its settings.</span></span> 
  
<span data-ttu-id="31ae3-138">MapiSvc.inf 文件包含一个提供程序列表，这些提供程序包含一个邮件服务以及每个提供程序的属性。</span><span class="sxs-lookup"><span data-stu-id="31ae3-138">The MapiSvc.inf file contains the list of providers that make up a message service and the properties for each.</span></span> <span data-ttu-id="31ae3-139">**CreateMsgService** 首先为邮件服务创建新的配置文件节，然后将该服务的所有信息从 MapiSvc.inf 文件复制到配置文件中，并为每个提供程序创建新节。</span><span class="sxs-lookup"><span data-stu-id="31ae3-139">**CreateMsgService** first creates a new profile section for the message service and then copies all of the information for that service from the MapiSvc.inf file into the profile, creating new sections for each provider.</span></span> 
  
<span data-ttu-id="31ae3-140">从 MapiSvc.inf 复制所有信息后，使用  _ulContext_ 参数中设置的 MSG_SERVICE_CREATE 值调用邮件服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="31ae3-140">After all the information has been copied from MapiSvc.inf, the message service's entry point function is called with the MSG_SERVICE_CREATE value set in the  _ulContext_ parameter.</span></span> <span data-ttu-id="31ae3-141">如果在 **CreateMsgService** 方法的  _ulFlags_ 参数中设置了 SERVICE_UI_ALLOWED 标志，则调用邮件服务的入口点函数时，也会传递  _ulUIParam_ 和  _ulFlags_ 参数中的值。</span><span class="sxs-lookup"><span data-stu-id="31ae3-141">If the SERVICE_UI_ALLOWED flag is set in the **CreateMsgService** method's  _ulFlags_ parameter, the values in the  _ulUIParam_ and  _ulFlags_ parameters are also passed when the message service's entry point function is called.</span></span> <span data-ttu-id="31ae3-142">服务提供商应显示其配置属性表，以便用户可以配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="31ae3-142">Service providers should display their configuration property sheets so users can configure the message service.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="31ae3-143">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="31ae3-143">Notes to callers</span></span>

 <span data-ttu-id="31ae3-144">**CreateMsgService** 不会返回已添加到配置文件的邮件服务的 [MAPIUID](mapiuid.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="31ae3-144">**CreateMsgService** does not return the [MAPIUID](mapiuid.md) structure for the message service that was added to the profile.</span></span> 
  
<span data-ttu-id="31ae3-145">若要检索已创建邮件服务的 **MAPIUID，** 请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="31ae3-145">To retrieve the **MAPIUID** for the created message service, use the following procedure:</span></span> 
  
1. <span data-ttu-id="31ae3-146">调用 [IMsgServiceAdmin：：GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) 方法来获取邮件服务管理表。</span><span class="sxs-lookup"><span data-stu-id="31ae3-146">Call the [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) method to get the message service administration table.</span></span> 
    
2. <span data-ttu-id="31ae3-147">通过限制与 **PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) 属性与邮件服务名称匹配的表，找到代表邮件服务的行。</span><span class="sxs-lookup"><span data-stu-id="31ae3-147">Locate the row that represents the message service by placing a restriction on the table that matches the **PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) property with the name of the message service.</span></span> 
    
3. <span data-ttu-id="31ae3-148">使用 [PidTagServiceUid](pidtagserviceuid-canonical-property.md) **PR_SERVICE_UID (** 检索服务) 属性。</span><span class="sxs-lookup"><span data-stu-id="31ae3-148">Retrieve the service's **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property.</span></span> 
    
4. <span data-ttu-id="31ae3-149">将 _lpUid_ 参数 **中 PR_SERVICE_UID** 属性的值传递到 [IMsgServiceAdmin：：ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法以配置该服务。</span><span class="sxs-lookup"><span data-stu-id="31ae3-149">Pass the value of the **PR_SERVICE_UID** property in the  _lpUid_ parameter to the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method to configure the service.</span></span> 
    
> [!CAUTION]
> <span data-ttu-id="31ae3-150">MAPI Microsoft Outlook 2010的实现不支持MAPI_UNICODE并且使用时将失败。</span><span class="sxs-lookup"><span data-stu-id="31ae3-150">The Microsoft Outlook 2010 implementation of the MAPI subsystem does not support MAPI_UNICODE and will fail if it is used.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="31ae3-151">_ulFlags_ SERVICE_NO_RESTART_WARNING当前具有的可下载头文件中未定义，在这种情况下，您可以使用以下值将其添加到代码中：>`#define SERVICE_NO_RESTART_WARNING 0x00000080`</span><span class="sxs-lookup"><span data-stu-id="31ae3-151">The  _ulFlags_ SERVICE_NO_RESTART_WARNING might not be defined in the downloadable header file you currently have, in which case you can add it to your code using the following value: >  `#define SERVICE_NO_RESTART_WARNING 0x00000080`</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="31ae3-152">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="31ae3-152">MFCMAPI reference</span></span>

<span data-ttu-id="31ae3-153">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="31ae3-153">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="31ae3-154">**文件**</span><span class="sxs-lookup"><span data-stu-id="31ae3-154">**File**</span></span>|<span data-ttu-id="31ae3-155">**函数**</span><span class="sxs-lookup"><span data-stu-id="31ae3-155">**Function**</span></span>|<span data-ttu-id="31ae3-156">**备注**</span><span class="sxs-lookup"><span data-stu-id="31ae3-156">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="31ae3-157">MAPIProfileFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="31ae3-157">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="31ae3-158">HrAddServiceToProfile</span><span class="sxs-lookup"><span data-stu-id="31ae3-158">HrAddServiceToProfile</span></span>  <br/> |<span data-ttu-id="31ae3-159">MFCMAPI 使用 **IMsgServiceAdmin：：CreateMsgService** 方法将服务添加到配置文件。</span><span class="sxs-lookup"><span data-stu-id="31ae3-159">MFCMAPI uses the **IMsgServiceAdmin::CreateMsgService** method to add a service to a profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="31ae3-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31ae3-160">See also</span></span>



[<span data-ttu-id="31ae3-161">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="31ae3-161">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="31ae3-162">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="31ae3-162">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

