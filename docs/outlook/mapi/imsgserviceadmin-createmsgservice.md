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
ms.openlocfilehash: 6e0bdd7108bacd17134592ac05ba71510fde76d8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775880"
---
# <a name="imsgserviceadmincreatemsgservice"></a><span data-ttu-id="8af14-103">IMsgServiceAdmin::CreateMsgService</span><span class="sxs-lookup"><span data-stu-id="8af14-103">IMsgServiceAdmin::CreateMsgService</span></span>

  
  
<span data-ttu-id="8af14-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8af14-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8af14-105">不建议使用： 建议使用[IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md) 。</span><span class="sxs-lookup"><span data-stu-id="8af14-105">Deprecated: The use of [IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md) is recommended.</span></span> <span data-ttu-id="8af14-106">向当前配置文件的消息服务。</span><span class="sxs-lookup"><span data-stu-id="8af14-106">Adds a message service to the current profile.</span></span> 
  
```cpp
HRESULT CreateMsgService(
  LPSTR lpszService,
  LPSTR lpszDisplayName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags    
);
```

## <a name="parameters"></a><span data-ttu-id="8af14-107">参数</span><span class="sxs-lookup"><span data-stu-id="8af14-107">Parameters</span></span>

 <span data-ttu-id="8af14-108">_lpszService_</span><span class="sxs-lookup"><span data-stu-id="8af14-108">_lpszService_</span></span>
  
> <span data-ttu-id="8af14-109">[in]一个指向要添加的消息服务的名称。</span><span class="sxs-lookup"><span data-stu-id="8af14-109">[in] A pointer to the name of the message service to add.</span></span> <span data-ttu-id="8af14-110">此消息服务名称必须出现在 MapiSvc.inf 文件的 **[服务]** 节中。</span><span class="sxs-lookup"><span data-stu-id="8af14-110">This message service name must appear in the **[Services]** section of the MapiSvc.inf file.</span></span> 
    
 <span data-ttu-id="8af14-111">_lpszDisplayName_</span><span class="sxs-lookup"><span data-stu-id="8af14-111">_lpszDisplayName_</span></span>
  
> <span data-ttu-id="8af14-112">[in]指向要添加的消息服务的显示名称的指针。</span><span class="sxs-lookup"><span data-stu-id="8af14-112">[in] A pointer to the display name of the message service to add.</span></span> <span data-ttu-id="8af14-113">如果邮件服务具有 MapiSvc.inf 文件中设置**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性，则忽略_lpszDisplayName_参数。</span><span class="sxs-lookup"><span data-stu-id="8af14-113">The  _lpszDisplayName_ parameter is ignored if the message service has set the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property in the MapiSvc.inf file.</span></span>
    
 <span data-ttu-id="8af14-114">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="8af14-114">_ulUIParam_</span></span>
  
> <span data-ttu-id="8af14-115">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="8af14-115">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span>
    
 <span data-ttu-id="8af14-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8af14-116">_ulFlags_</span></span>
  
> <span data-ttu-id="8af14-117">[in]位掩码的标志，控制如何安装邮件服务。</span><span class="sxs-lookup"><span data-stu-id="8af14-117">[in] A bitmask of flags that controls how the message service is installed.</span></span> <span data-ttu-id="8af14-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="8af14-118">The following flags can be set:</span></span>
    
<span data-ttu-id="8af14-119">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8af14-119">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="8af14-120">LpszService 和 lpszDisplayName 参数应强制转换为 LPWSTR 和解释为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="8af14-120">The lpszService and the lpszDisplayName parameters should be cast to LPWSTR and interpreted as Unicode strings.</span></span>
    
<span data-ttu-id="8af14-121">SERVICE_NO_RESTART_WARNING</span><span class="sxs-lookup"><span data-stu-id="8af14-121">SERVICE_NO_RESTART_WARNING</span></span>
  
> <span data-ttu-id="8af14-122">添加到配置文件的新消息服务时, MAPI 子系统，基于各种情况和条件，通常决定了此操作需要重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="8af14-122">When adding a new message service to the profile, the MAPI subsystem, based on various circumstances and criteria, often determines that this action requires a restart of Outlook.</span></span> <span data-ttu-id="8af14-123">如果 SERVICE_NO_RESTART_WARNING 标志不包括允许用户界面-基于 SERVICE_UI_ALWAYS 和 SERVICE_UI_ALLOWED 标志-和至少一个过程登录当前配置文件，此函数显示消息"您必须重新启动 Outlook这些更改才会生效。"</span><span class="sxs-lookup"><span data-stu-id="8af14-123">If the SERVICE_NO_RESTART_WARNING flag is not included and UI is allowed - based on the SERVICE_UI_ALWAYS and SERVICE_UI_ALLOWED flags - and at least one process is logged onto the current profile, this function displays the message "You must restart Outlook for these changes to take effect."</span></span> <span data-ttu-id="8af14-124">包括 SERVICE_NO_RESTART_WARNING 标志禁止显示该警告消息。</span><span class="sxs-lookup"><span data-stu-id="8af14-124">Including the SERVICE_NO_RESTART_WARNING flag suppresses the display of that warning message.</span></span>
    
<span data-ttu-id="8af14-125">SERVICE_UI_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="8af14-125">SERVICE_UI_ALLOWED</span></span>
  
> <span data-ttu-id="8af14-126">消息服务配置根据需要允许 UI。</span><span class="sxs-lookup"><span data-stu-id="8af14-126">The message service configuration UI is allowed if needed.</span></span>
    
<span data-ttu-id="8af14-127">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="8af14-127">SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="8af14-128">邮件服务显示其配置属性表。</span><span class="sxs-lookup"><span data-stu-id="8af14-128">The message service displays its configuration property sheet.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8af14-129">返回值</span><span class="sxs-lookup"><span data-stu-id="8af14-129">Return value</span></span>

<span data-ttu-id="8af14-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="8af14-130">S_OK</span></span> 
  
> <span data-ttu-id="8af14-131">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="8af14-131">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="8af14-132">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="8af14-132">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="8af14-133">消息服务名称不在的 MapiSvc.inf **[服务]** 部分。</span><span class="sxs-lookup"><span data-stu-id="8af14-133">The message service name is not in the **[Services]** section of MapiSvc.inf.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="8af14-134">说明</span><span class="sxs-lookup"><span data-stu-id="8af14-134">Remarks</span></span>

<span data-ttu-id="8af14-135">**IMsgServiceAdmin::CreateMsgService**方法将消息服务添加到当前配置文件。</span><span class="sxs-lookup"><span data-stu-id="8af14-135">The **IMsgServiceAdmin::CreateMsgService** method adds a message service to the current profile.</span></span> <span data-ttu-id="8af14-136">**CreateMsgService**调用消息服务的入口点函数，以执行任何特定于服务的配置任务。</span><span class="sxs-lookup"><span data-stu-id="8af14-136">**CreateMsgService** calls the message service's entry point function to perform any service-specific configuration tasks.</span></span> <span data-ttu-id="8af14-137">_UlFlags_参数中设置 SERVICE_UI_ALLOWED 标志，如果要安装的消息服务可以显示属性表可让用户能够配置其设置。</span><span class="sxs-lookup"><span data-stu-id="8af14-137">If the SERVICE_UI_ALLOWED flag is set in the  _ulFlags_ parameter, the message service being installed can display a property sheet to enable the user to configure its settings.</span></span> 
  
<span data-ttu-id="8af14-138">MapiSvc.inf 文件包含每个组成的消息服务和属性的提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="8af14-138">The MapiSvc.inf file contains the list of providers that make up a message service and the properties for each.</span></span> <span data-ttu-id="8af14-139">**CreateMsgService**首先创建新的配置文件部分消息服务，然后复制该服务的信息的所有从 MapiSvc.inf 文件到配置文件，为每个提供程序创建新的部分。</span><span class="sxs-lookup"><span data-stu-id="8af14-139">**CreateMsgService** first creates a new profile section for the message service and then copies all of the information for that service from the MapiSvc.inf file into the profile, creating new sections for each provider.</span></span> 
  
<span data-ttu-id="8af14-140">已从 MapiSvc.inf 复制所有信息后，使用_ulContext_参数中设置的 MSG_SERVICE_CREATE 值调用消息服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="8af14-140">After all the information has been copied from MapiSvc.inf, the message service's entry point function is called with the MSG_SERVICE_CREATE value set in the  _ulContext_ parameter.</span></span> <span data-ttu-id="8af14-141">如果**CreateMsgService**方法的_ulFlags_参数中设置 SERVICE_UI_ALLOWED 标志，消息服务的入口点函数调用时还传递的_ulUIParam_和_ulFlags_参数中的值。</span><span class="sxs-lookup"><span data-stu-id="8af14-141">If the SERVICE_UI_ALLOWED flag is set in the **CreateMsgService** method's  _ulFlags_ parameter, the values in the  _ulUIParam_ and  _ulFlags_ parameters are also passed when the message service's entry point function is called.</span></span> <span data-ttu-id="8af14-142">服务提供商应显示其配置属性表，以便用户可以配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="8af14-142">Service providers should display their configuration property sheets so users can configure the message service.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="8af14-143">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="8af14-143">Notes to callers</span></span>

 <span data-ttu-id="8af14-144">**CreateMsgService**不返回邮件服务已添加到配置文件的[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="8af14-144">**CreateMsgService** does not return the [MAPIUID](mapiuid.md) structure for the message service that was added to the profile.</span></span> 
  
<span data-ttu-id="8af14-145">若要检索**MAPIUID**创建的消息服务，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="8af14-145">To retrieve the **MAPIUID** for the created message service, use the following procedure:</span></span> 
  
1. <span data-ttu-id="8af14-146">调用[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)方法以获取邮件服务管理表。</span><span class="sxs-lookup"><span data-stu-id="8af14-146">Call the [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) method to get the message service administration table.</span></span> 
    
2. <span data-ttu-id="8af14-147">找到表示邮件服务通过将限制放在表的**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) 属性与消息服务的名称相匹配的行。</span><span class="sxs-lookup"><span data-stu-id="8af14-147">Locate the row that represents the message service by placing a restriction on the table that matches the **PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) property with the name of the message service.</span></span> 
    
3. <span data-ttu-id="8af14-148">检索服务的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="8af14-148">Retrieve the service's **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property.</span></span> 
    
4. <span data-ttu-id="8af14-149">将**PR_SERVICE_UID**属性的值_lpUid_参数中传递给[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法，以配置服务。</span><span class="sxs-lookup"><span data-stu-id="8af14-149">Pass the value of the **PR_SERVICE_UID** property in the  _lpUid_ parameter to the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method to configure the service.</span></span> 
    
> [!CAUTION]
> <span data-ttu-id="8af14-150">Microsoft Outlook 2010 实现的 MAPI 子系统不支持 MAPI_UNICODE，如果使用它将失败。</span><span class="sxs-lookup"><span data-stu-id="8af14-150">The Microsoft Outlook 2010 implementation of the MAPI subsystem does not support MAPI_UNICODE and will fail if it is used.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8af14-151">_UlFlags_ SERVICE_NO_RESTART_WARNING 可能未定义当前具有可下载头文件中，在这种情况下您可以将其添加到代码中使用以下值： >`#define SERVICE_NO_RESTART_WARNING 0x00000080`</span><span class="sxs-lookup"><span data-stu-id="8af14-151">The  _ulFlags_ SERVICE_NO_RESTART_WARNING might not be defined in the downloadable header file you currently have, in which case you can add it to your code using the following value: >  `#define SERVICE_NO_RESTART_WARNING 0x00000080`</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="8af14-152">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="8af14-152">MFCMAPI reference</span></span>

<span data-ttu-id="8af14-153">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="8af14-153">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="8af14-154">**文件**</span><span class="sxs-lookup"><span data-stu-id="8af14-154">**File**</span></span>|<span data-ttu-id="8af14-155">**函数**</span><span class="sxs-lookup"><span data-stu-id="8af14-155">**Function**</span></span>|<span data-ttu-id="8af14-156">**Comment**</span><span class="sxs-lookup"><span data-stu-id="8af14-156">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8af14-157">MAPIProfileFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="8af14-157">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="8af14-158">HrAddServiceToProfile</span><span class="sxs-lookup"><span data-stu-id="8af14-158">HrAddServiceToProfile</span></span>  <br/> |<span data-ttu-id="8af14-159">MFCMAPI 使用**IMsgServiceAdmin::CreateMsgService**方法向一个配置文件中添加服务。</span><span class="sxs-lookup"><span data-stu-id="8af14-159">MFCMAPI uses the **IMsgServiceAdmin::CreateMsgService** method to add a service to a profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8af14-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8af14-160">See also</span></span>



[<span data-ttu-id="8af14-161">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8af14-161">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="8af14-162">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="8af14-162">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

