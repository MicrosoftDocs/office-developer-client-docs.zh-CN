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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b7fe25491228f00f6865af963db36f27bae5d7a7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410180"
---
# <a name="imsgserviceadmin2createmsgserviceex"></a><span data-ttu-id="d0032-103">IMsgServiceAdmin2::CreateMsgServiceEx</span><span class="sxs-lookup"><span data-stu-id="d0032-103">IMsgServiceAdmin2::CreateMsgServiceEx</span></span>

  
  
<span data-ttu-id="d0032-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d0032-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d0032-105">将邮件服务添加到当前配置文件, 并返回新添加的服务 UID。</span><span class="sxs-lookup"><span data-stu-id="d0032-105">Adds a message service to the current profile and returns that newly added service UID.</span></span>
  
```cpp
HRESULT CreateMsgServiceEx(
  LPSTR lpszService,
  LPSTR lpszDisplayName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,    
  LPMAPIUID lpuidService
);
```

## <a name="parameters"></a><span data-ttu-id="d0032-106">参数</span><span class="sxs-lookup"><span data-stu-id="d0032-106">Parameters</span></span>

 <span data-ttu-id="d0032-107">_lpszService_</span><span class="sxs-lookup"><span data-stu-id="d0032-107">_lpszService_</span></span>
  
> <span data-ttu-id="d0032-108">实时指向要添加的邮件服务的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="d0032-108">[in] A pointer to the name of the message service to add.</span></span> <span data-ttu-id="d0032-109">此邮件服务名称必须出现在 mapisvc.inf 文件的 "**服务**" 部分中。</span><span class="sxs-lookup"><span data-stu-id="d0032-109">This message service name must appear in the **[Services]** section of the MapiSvc.inf file.</span></span> 
    
 <span data-ttu-id="d0032-110">_lpszDisplayName_</span><span class="sxs-lookup"><span data-stu-id="d0032-110">_lpszDisplayName_</span></span>
  
> <span data-ttu-id="d0032-111">实时指向要添加的邮件服务的显示名称的指针。</span><span class="sxs-lookup"><span data-stu-id="d0032-111">[in] A pointer to the display name of the message service to add.</span></span> <span data-ttu-id="d0032-112">如果邮件服务已在 mapisvc.inf 文件中设置了**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性, 则会忽略_lpszDisplayName_参数。</span><span class="sxs-lookup"><span data-stu-id="d0032-112">The  _lpszDisplayName_ parameter is ignored if the message service has set the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property in the MapiSvc.inf file.</span></span>
    
 <span data-ttu-id="d0032-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="d0032-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="d0032-114">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="d0032-114">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span>
    
 <span data-ttu-id="d0032-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d0032-115">_ulFlags_</span></span>
  
> <span data-ttu-id="d0032-116">实时用于控制如何安装邮件服务的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="d0032-116">[in] A bitmask of flags that controls how the message service is installed.</span></span> <span data-ttu-id="d0032-117">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="d0032-117">The following flags can be set:</span></span>
    
<span data-ttu-id="d0032-118">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d0032-118">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="d0032-119">应将 lpszService 和 lpszDisplayName 参数强制转换为 LPWSTR, 并将其解释为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="d0032-119">The lpszService and the lpszDisplayName parameters should be cast to LPWSTR and interpreted as Unicode strings.</span></span>
    
<span data-ttu-id="d0032-120">SERVICE_NO_RESTART_WARNING</span><span class="sxs-lookup"><span data-stu-id="d0032-120">SERVICE_NO_RESTART_WARNING</span></span>
  
> <span data-ttu-id="d0032-121">将新的邮件服务添加到配置文件时, 基于各种情况和标准的 MAPI 子系统通常会确定此操作需要重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="d0032-121">When adding a new message service to the profile, the MAPI subsystem, based on various circumstances and criteria, often determines that this action requires a restart of Outlook.</span></span> <span data-ttu-id="d0032-122">如果不包含 SERVICE_NO_RESTART_WARNING 标志且允许 UI (基于 SERVICE_UI_ALWAYS 和 SERVICE_UI_ALLOWED 标志), 并且至少有一个进程登录到当前配置文件, 则此函数将显示消息 "您必须重新启动 Outlook for这些更改才能生效。 "</span><span class="sxs-lookup"><span data-stu-id="d0032-122">If the SERVICE_NO_RESTART_WARNING flag is not included and UI is allowed - based on the SERVICE_UI_ALWAYS and SERVICE_UI_ALLOWED flags - and at least one process is logged onto the current profile, this function displays the message "You must restart Outlook for these changes to take effect."</span></span> <span data-ttu-id="d0032-123">包括 SERVICE_NO_RESTART_WARNING 标志禁止显示该警告消息。</span><span class="sxs-lookup"><span data-stu-id="d0032-123">Including the SERVICE_NO_RESTART_WARNING flag suppresses the display of that warning message.</span></span>
    
<span data-ttu-id="d0032-124">SERVICE_UI_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="d0032-124">SERVICE_UI_ALLOWED</span></span>
  
> <span data-ttu-id="d0032-125">如果需要, 允许使用邮件服务配置 UI。</span><span class="sxs-lookup"><span data-stu-id="d0032-125">The message service configuration UI is allowed if needed.</span></span>
    
<span data-ttu-id="d0032-126">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="d0032-126">SERVICE_UI_ALWAYS</span></span>
  
> <span data-ttu-id="d0032-127">邮件服务显示其配置属性表。</span><span class="sxs-lookup"><span data-stu-id="d0032-127">The message service displays its configuration property sheet.</span></span>
    
 <span data-ttu-id="d0032-128">_lpuidService_</span><span class="sxs-lookup"><span data-stu-id="d0032-128">_lpuidService_</span></span>
  
> <span data-ttu-id="d0032-129">排除指向添加的邮件服务的 UID 的指针。</span><span class="sxs-lookup"><span data-stu-id="d0032-129">[out] The pointer to the UID of the message service added.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d0032-130">返回值</span><span class="sxs-lookup"><span data-stu-id="d0032-130">Return value</span></span>

<span data-ttu-id="d0032-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0032-131">S_OK</span></span>
  
> <span data-ttu-id="d0032-132">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="d0032-132">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="d0032-133">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="d0032-133">MAPI_E_NOT_FOUND</span></span>
  
> <span data-ttu-id="d0032-134">邮件服务名称不在 mapisvc.inf 的 "**服务**" 部分中。</span><span class="sxs-lookup"><span data-stu-id="d0032-134">The message service name is not in the **[Services]** section of MapiSvc.inf.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d0032-135">说明</span><span class="sxs-lookup"><span data-stu-id="d0032-135">Remarks</span></span>

<span data-ttu-id="d0032-136">**IMsgServiceAdmin2:: CreateMsgServiceEx**方法将邮件服务添加到当前配置文件中。</span><span class="sxs-lookup"><span data-stu-id="d0032-136">The **IMsgServiceAdmin2::CreateMsgServiceEx** method adds a message service to the current profile.</span></span> <span data-ttu-id="d0032-137">**CreateMsgServiceEx**调用邮件服务的入口点函数以执行任何特定于服务的配置任务。</span><span class="sxs-lookup"><span data-stu-id="d0032-137">**CreateMsgServiceEx** calls the message service's entry point function to perform any service-specific configuration tasks.</span></span> <span data-ttu-id="d0032-138">如果在_ulFlags_参数中设置了 SERVICE_UI_ALLOWED 标志, 则要安装的邮件服务可以显示一个属性表, 使用户可以配置其设置。</span><span class="sxs-lookup"><span data-stu-id="d0032-138">If the SERVICE_UI_ALLOWED flag is set in the  _ulFlags_ parameter, the message service being installed can display a property sheet enabling the user to configure its settings.</span></span> 
  
<span data-ttu-id="d0032-139">mapisvc.inf 文件包含组成邮件服务的提供程序的列表以及每个提供程序的属性。</span><span class="sxs-lookup"><span data-stu-id="d0032-139">The MapiSvc.inf file contains the list of providers that make up a message service and the properties for each.</span></span> <span data-ttu-id="d0032-140">**CreateMsgServiceEx**首先为邮件服务创建一个新的配置文件部分, 然后将该服务的所有信息从 mapisvc.inf 文件复制到配置文件中, 为每个提供程序创建新的分区。</span><span class="sxs-lookup"><span data-stu-id="d0032-140">**CreateMsgServiceEx** first creates a new profile section for the message service and then copies all of the information for that service from the MapiSvc.inf file into the profile, creating new sections for each provider.</span></span> 
  
<span data-ttu-id="d0032-141">从 mapisvc.inf 复制完所有信息后, 将使用_ulContext_参数中设置的 MSG_SERVICE_CREATE 值调用邮件服务的入口点函数**MSGSERVICEENTRY**。</span><span class="sxs-lookup"><span data-stu-id="d0032-141">After all the information has been copied from MapiSvc.inf, the message service's entry point function, **MSGSERVICEENTRY**, is called with the MSG_SERVICE_CREATE value set in the  _ulContext_ parameter.</span></span> <span data-ttu-id="d0032-142">如果在**CreateMsgServiceEx**方法的_ulFlags_参数中设置了 SERVICE_UI_ALLOWED 标志, 则在调用邮件服务的入口点函数时, 也会传递_ulUIParam_和_ulFlags_参数中的值。</span><span class="sxs-lookup"><span data-stu-id="d0032-142">If the SERVICE_UI_ALLOWED flag is set in the **CreateMsgServiceEx** method's  _ulFlags_ parameter, the values in the  _ulUIParam_ and  _ulFlags_ parameters are also passed when the message service's entry point function is called.</span></span> <span data-ttu-id="d0032-143">服务提供商应显示其配置属性表, 以便用户可以配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="d0032-143">Service providers should display their configuration property sheets so users can configure the message service.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d0032-144">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d0032-144">Notes to callers</span></span>

<span data-ttu-id="d0032-145">如果**CreateMsgServiceEx** _lpuidService_参数不为 NULL, 则添加到配置文件中的邮件服务的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性将在它所指向的**GUID**中返回。</span><span class="sxs-lookup"><span data-stu-id="d0032-145">If the **CreateMsgServiceEx** _lpuidService_ argument is not NULL, the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property of the message service that was added to the profile is returned in the **GUID** to which it points.</span></span> 
  
<span data-ttu-id="d0032-146">将_lpuidService_参数中的**PR_SERVICE_UID**属性的值传递给[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法以配置服务。</span><span class="sxs-lookup"><span data-stu-id="d0032-146">Pass the value of the **PR_SERVICE_UID** property in the  _lpuidService_ parameter to the [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) method to configure the service.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="d0032-147">MAPI 子系统的 Microsoft Outlook 2010 实现不支持 MAPI_UNICODE, 如果使用, 将会失败。</span><span class="sxs-lookup"><span data-stu-id="d0032-147">The Microsoft Outlook 2010 implementation of the MAPI subsystem does not support MAPI_UNICODE and will fail if it is used.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d0032-148">IMsgServiceAdmin2 接口由实现 IMsgServiceAdmin 接口的同一对象公开, 并已在 outlook 2003 后使用 outlook 的 MAPI 子系统实现提供。</span><span class="sxs-lookup"><span data-stu-id="d0032-148">The IMsgServiceAdmin2 interface is exposed by the same object that implements the IMsgServiceAdmin interface, and has been available using Outlook's implementation of the MAPI subsystem since Outlook 2003.</span></span> <span data-ttu-id="d0032-149">其 IID `#if !defined(INITGUID) || defined(USES_IID_IMsgServiceAdmin2)` >   `DEFINE_OLEGUID(IID_IMsgServiceAdmin2,0x00020387, 0, 0);`定义如下: > > _ulFlags_ SERVICE_NO_RESTART_WARNING 可能未在您当前拥有的可下载头文件中定义, 在这种情况下, 您可以使用以下值将其添加到代码中: >`#define SERVICE_NO_RESTART_WARNING 0x00000080`</span><span class="sxs-lookup"><span data-stu-id="d0032-149">Its IID is defined as follows: >  `#if !defined(INITGUID) || defined(USES_IID_IMsgServiceAdmin2)`>  `DEFINE_OLEGUID(IID_IMsgServiceAdmin2,0x00020387, 0, 0);`> The  _ulFlags_ SERVICE_NO_RESTART_WARNING might not be defined in the downloadable header file you currently have, in which case you can add it to your code using the following value: >  `#define SERVICE_NO_RESTART_WARNING 0x00000080`</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d0032-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0032-150">See also</span></span>



[<span data-ttu-id="d0032-151">IMsgServiceAdmin2 : IMsgServiceAdmin</span><span class="sxs-lookup"><span data-stu-id="d0032-151">IMsgServiceAdmin2 : IMsgServiceAdmin</span></span>](imsgserviceadmin2imsgserviceadmin.md)


[<span data-ttu-id="d0032-152">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d0032-152">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

