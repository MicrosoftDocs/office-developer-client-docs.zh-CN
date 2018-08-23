---
title: IMsgServiceAdmin2CreateMsgServiceEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin2.CreateMsgServiceEx
api_type:
- COM
ms.assetid: 4910dabd-9380-4fde-a440-5c64d74c0bba
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f700389315ca7bd184a9d6defb0b44eaec99a38e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574774"
---
# <a name="imsgserviceadmin2createmsgserviceex"></a><span data-ttu-id="4a4c1-103">IMsgServiceAdmin2::CreateMsgServiceEx</span><span class="sxs-lookup"><span data-stu-id="4a4c1-103">IMsgServiceAdmin2::CreateMsgServiceEx</span></span>

  
  
<span data-ttu-id="4a4c1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a4c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a4c1-105">向当前配置文件和新添加的服务 UID 的返回的消息服务。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-105">Adds a message service to the current profile and returns that newly added service UID.</span></span>
  
```cpp
HRESULT CreateMsgServiceEx(
  LPSTR lpszService,
  LPSTR lpszDisplayName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,    
  LPMAPIUID lpuidService
);
```

## <a name="parameters"></a><span data-ttu-id="4a4c1-106">参数</span><span class="sxs-lookup"><span data-stu-id="4a4c1-106">Parameters</span></span>

 <span data-ttu-id="4a4c1-107">_lpszService_</span><span class="sxs-lookup"><span data-stu-id="4a4c1-107">_lpszService_</span></span>
  
> <span data-ttu-id="4a4c1-108">[in]一个指向要添加的消息服务的名称。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-108">[in] A pointer to the name of the message service to add.</span></span> <span data-ttu-id="4a4c1-109">此消息服务名称必须出现在 MapiSvc.inf 文件的 **[服务]** 节中。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-109">This message service name must appear in the **[Services]** section of the MapiSvc.inf file.</span></span> 
    
 <span data-ttu-id="4a4c1-110">_lpszDisplayName_</span><span class="sxs-lookup"><span data-stu-id="4a4c1-110">_lpszDisplayName_</span></span>
  
> <span data-ttu-id="4a4c1-111">[in]指向要添加的消息服务的显示名称的指针。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-111">[in] A pointer to the display name of the message service to add.</span></span> <span data-ttu-id="4a4c1-112">如果邮件服务具有 MapiSvc.inf 文件中设置**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性，则忽略_lpszDisplayName_参数。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-112">The  _lpszDisplayName_ parameter is ignored if the message service has set the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property in the MapiSvc.inf file.</span></span>
    
 <span data-ttu-id="4a4c1-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="4a4c1-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="4a4c1-114">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-114">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span>
    
 <span data-ttu-id="4a4c1-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="4a4c1-115">_ulFlags_</span></span>
  
> <span data-ttu-id="4a4c1-116">[in]位掩码的标志，控制如何安装邮件服务。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-116">[in] A bitmask of flags that controls how the message service is installed.</span></span> <span data-ttu-id="4a4c1-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="4a4c1-117">The following flags can be set:</span></span>
    
<span data-ttu-id="4a4c1-118">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4a4c1-118">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="4a4c1-119">LpszService 和 lpszDisplayName 参数应强制转换为 LPWSTR 和解释为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-119">The lpszService and the lpszDisplayName parameters should be cast to LPWSTR and interpreted as Unicode strings.</span></span>
    
<span data-ttu-id="4a4c1-120">SERVICE_NO_RESTART_WARNING</span><span class="sxs-lookup"><span data-stu-id="4a4c1-120">SERVICE_NO_RESTART_WARNING</span></span>
  
> <span data-ttu-id="4a4c1-121">添加到配置文件的新消息服务时, MAPI 子系统，基于各种情况和条件，通常决定了此操作需要重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-121">When adding a new message service to the profile, the MAPI subsystem, based on various circumstances and criteria, often determines that this action requires a restart of Outlook.</span></span> <span data-ttu-id="4a4c1-122">如果 SERVICE_NO_RESTART_WARNING 标志不包括允许用户界面-基于 SERVICE_UI_ALWAYS 和 SERVICE_UI_ALLOWED 标志-和至少一个过程登录当前配置文件，此函数显示消息"您必须重新启动 Outlook这些更改才会生效。"</span><span class="sxs-lookup"><span data-stu-id="4a4c1-122">If the SERVICE_NO_RESTART_WARNING flag is not included and UI is allowed - based on the SERVICE_UI_ALWAYS and SERVICE_UI_ALLOWED flags - and at least one process is logged onto the current profile, this function displays the message "You must restart Outlook for these changes to take effect."</span></span> <span data-ttu-id="4a4c1-123">包括 SERVICE_NO_RESTART_WARNING 标志禁止显示该警告消息。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-123">Including the SERVICE_NO_RESTART_WARNING flag suppresses the display of that warning message.</span></span>
    
<span data-ttu-id="4a4c1-124">SERVICE_UI_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="4a4c1-124">SERVICE_UI_ALLOWED</span></span>
  
> <span data-ttu-id="4a4c1-125">消息服务配置根据需要允许 UI。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-125">The message service configuration UI is allowed if needed.</span></span>
    
<span data-ttu-id="4a4c1-126">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="4a4c1-126">SERVICE_UI_ALWAYS</span></span>
  
> <span data-ttu-id="4a4c1-127">邮件服务显示其配置属性表。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-127">The message service displays its configuration property sheet.</span></span>
    
 <span data-ttu-id="4a4c1-128">_lpuidService_</span><span class="sxs-lookup"><span data-stu-id="4a4c1-128">_lpuidService_</span></span>
  
> <span data-ttu-id="4a4c1-129">[输出]指向的 UID 添加消息服务的指针。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-129">[out] The pointer to the UID of the message service added.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4a4c1-130">返回值</span><span class="sxs-lookup"><span data-stu-id="4a4c1-130">Return value</span></span>

<span data-ttu-id="4a4c1-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a4c1-131">S_OK</span></span>
  
> <span data-ttu-id="4a4c1-132">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-132">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="4a4c1-133">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="4a4c1-133">MAPI_E_NOT_FOUND</span></span>
  
> <span data-ttu-id="4a4c1-134">消息服务名称不在的 MapiSvc.inf **[服务]** 部分。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-134">The message service name is not in the **[Services]** section of MapiSvc.inf.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="4a4c1-135">注解</span><span class="sxs-lookup"><span data-stu-id="4a4c1-135">Remarks</span></span>

<span data-ttu-id="4a4c1-136">**IMsgServiceAdmin2::CreateMsgServiceEx**方法将消息服务添加到当前配置文件。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-136">The **IMsgServiceAdmin2::CreateMsgServiceEx** method adds a message service to the current profile.</span></span> <span data-ttu-id="4a4c1-137">**CreateMsgServiceEx**调用消息服务的入口点函数，以执行任何特定于服务的配置任务。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-137">**CreateMsgServiceEx** calls the message service's entry point function to perform any service-specific configuration tasks.</span></span> <span data-ttu-id="4a4c1-138">如果_ulFlags_参数中设置 SERVICE_UI_ALLOWED 标志，指示正在安装该消息服务可以显示使用户可以配置其设置的属性表。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-138">If the SERVICE_UI_ALLOWED flag is set in the  _ulFlags_ parameter, the message service being installed can display a property sheet enabling the user to configure its settings.</span></span> 
  
<span data-ttu-id="4a4c1-139">MapiSvc.inf 文件包含每个组成的消息服务和属性的提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-139">The MapiSvc.inf file contains the list of providers that make up a message service and the properties for each.</span></span> <span data-ttu-id="4a4c1-140">**CreateMsgServiceEx**首先创建新的配置文件部分消息服务，然后复制该服务的信息的所有从 MapiSvc.inf 文件到配置文件，为每个提供程序创建新的部分。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-140">**CreateMsgServiceEx** first creates a new profile section for the message service and then copies all of the information for that service from the MapiSvc.inf file into the profile, creating new sections for each provider.</span></span> 
  
<span data-ttu-id="4a4c1-141">已从 MapiSvc.inf 复制所有信息后，该消息服务的入口点函数， **MSGSERVICEENTRY**，使用_ulContext_参数中设置的 MSG_SERVICE_CREATE 值调用。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-141">After all the information has been copied from MapiSvc.inf, the message service's entry point function, **MSGSERVICEENTRY**, is called with the MSG_SERVICE_CREATE value set in the  _ulContext_ parameter.</span></span> <span data-ttu-id="4a4c1-142">如果**CreateMsgServiceEx**方法的_ulFlags_参数中设置 SERVICE_UI_ALLOWED 标志，消息服务的入口点函数调用时还传递的_ulUIParam_和_ulFlags_参数中的值。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-142">If the SERVICE_UI_ALLOWED flag is set in the **CreateMsgServiceEx** method's  _ulFlags_ parameter, the values in the  _ulUIParam_ and  _ulFlags_ parameters are also passed when the message service's entry point function is called.</span></span> <span data-ttu-id="4a4c1-143">服务提供商应显示其配置属性表，以便用户可以配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-143">Service providers should display their configuration property sheets so users can configure the message service.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="4a4c1-144">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="4a4c1-144">Notes to callers</span></span>

<span data-ttu-id="4a4c1-145">如果**CreateMsgServiceEx** _lpuidService_参数不是 NULL，邮件服务已添加到配置文件的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性将返回它指向的**GUID** 。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-145">If the **CreateMsgServiceEx** _lpuidService_ argument is not NULL, the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property of the message service that was added to the profile is returned in the **GUID** to which it points.</span></span> 
  
<span data-ttu-id="4a4c1-146">将**PR_SERVICE_UID**属性的值_lpuidService_参数中传递给[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法，以配置服务。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-146">Pass the value of the **PR_SERVICE_UID** property in the  _lpuidService_ parameter to the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method to configure the service.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="4a4c1-147">Microsoft Outlook 2010 实现的 MAPI 子系统不支持 MAPI_UNICODE，如果使用它将失败。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-147">The Microsoft Outlook 2010 implementation of the MAPI subsystem does not support MAPI_UNICODE and will fail if it is used.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4a4c1-148">IMsgServiceAdmin2 接口将公开相同对象实现 IMsgServiceAdmin 接口，并已可使用的 MAPI 子系统相 Outlook 2003 的 Outlook 的实现。</span><span class="sxs-lookup"><span data-stu-id="4a4c1-148">The IMsgServiceAdmin2 interface is exposed by the same object that implements the IMsgServiceAdmin interface, and has been available using Outlook's implementation of the MAPI subsystem since Outlook 2003.</span></span> <span data-ttu-id="4a4c1-149">其 IID，如下所示定义： > `#if !defined(INITGUID) || defined(USES_IID_IMsgServiceAdmin2)` >   `DEFINE_OLEGUID(IID_IMsgServiceAdmin2,0x00020387, 0, 0);`> _ulFlags_ SERVICE_NO_RESTART_WARNING 可能未定义当前具有可下载头文件中，在这种情况下您可以将其添加到代码中使用以下值： >`#define SERVICE_NO_RESTART_WARNING 0x00000080`</span><span class="sxs-lookup"><span data-stu-id="4a4c1-149">Its IID is defined as follows: >  `#if !defined(INITGUID) || defined(USES_IID_IMsgServiceAdmin2)`>  `DEFINE_OLEGUID(IID_IMsgServiceAdmin2,0x00020387, 0, 0);`> The  _ulFlags_ SERVICE_NO_RESTART_WARNING might not be defined in the downloadable header file you currently have, in which case you can add it to your code using the following value: >  `#define SERVICE_NO_RESTART_WARNING 0x00000080`</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a4c1-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a4c1-150">See also</span></span>



[<span data-ttu-id="4a4c1-151">IMsgServiceAdmin2 : IMsgServiceAdmin</span><span class="sxs-lookup"><span data-stu-id="4a4c1-151">IMsgServiceAdmin2 : IMsgServiceAdmin</span></span>](imsgserviceadmin2imsgserviceadmin.md)


[<span data-ttu-id="4a4c1-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="4a4c1-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

