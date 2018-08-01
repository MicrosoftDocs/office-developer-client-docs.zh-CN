---
title: IMsgServiceAdminConfigureMsgService
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.ConfigureMsgService
api_type:
- COM
ms.assetid: a08f5905-2585-49ca-abb7-a77f2736f604
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f58d0f5cd7dfe74d3859d4f06a41aad6c3a55ac4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775828"
---
# <a name="imsgserviceadminconfiguremsgservice"></a><span data-ttu-id="6e745-103">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="6e745-103">IMsgServiceAdmin::ConfigureMsgService</span></span>

  
  
<span data-ttu-id="6e745-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6e745-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6e745-105">重新配置的消息服务。</span><span class="sxs-lookup"><span data-stu-id="6e745-105">Reconfigures a message service.</span></span>
  
```cpp
HRESULT ConfigureMsgService(
  LPMAPIUID lpUID,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG cValues,
  LPSPropValue lpProps
);
```

## <a name="parameters"></a><span data-ttu-id="6e745-106">参数</span><span class="sxs-lookup"><span data-stu-id="6e745-106">Parameters</span></span>

 <span data-ttu-id="6e745-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="6e745-107">_lpUID_</span></span>
  
> <span data-ttu-id="6e745-108">[in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要配置的消息服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6e745-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the message service to configure.</span></span> 
    
 <span data-ttu-id="6e745-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="6e745-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="6e745-110">[in]配置属性表的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="6e745-110">[in] A handle to the parent window of the configuration property sheet.</span></span>
    
 <span data-ttu-id="6e745-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6e745-111">_ulFlags_</span></span>
  
> <span data-ttu-id="6e745-112">[in]位掩码的标志的控件显示的属性表。</span><span class="sxs-lookup"><span data-stu-id="6e745-112">[in] A bitmask of flags that controls the display of the property sheet.</span></span> <span data-ttu-id="6e745-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="6e745-113">The following flags can be set:</span></span>
    
<span data-ttu-id="6e745-114">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6e745-114">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="6e745-115">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="6e745-115">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="6e745-116">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="6e745-116">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="6e745-117">MSG_SERVICE_UI_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="6e745-117">MSG_SERVICE_UI_READ_ONLY</span></span> 
  
> <span data-ttu-id="6e745-118">邮件服务应显示其配置属性表，但不是使用户能够更改它。</span><span class="sxs-lookup"><span data-stu-id="6e745-118">The message service should display its configuration property sheet but not enable the user to change it.</span></span> <span data-ttu-id="6e745-119">大多数消息服务忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="6e745-119">Most message services ignore this flag.</span></span>
    
<span data-ttu-id="6e745-120">SERVICE_UI_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="6e745-120">SERVICE_UI_ALLOWED</span></span> 
  
> <span data-ttu-id="6e745-121">邮件服务应显示其配置属性表，仅当不完全配置该服务。</span><span class="sxs-lookup"><span data-stu-id="6e745-121">The message service should display its configuration property sheet only if the service is not completely configured.</span></span>
    
<span data-ttu-id="6e745-122">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="6e745-122">SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="6e745-123">邮件服务必须始终显示其配置属性表。</span><span class="sxs-lookup"><span data-stu-id="6e745-123">The message service must always display its configuration property sheet.</span></span> <span data-ttu-id="6e745-124">如果未设置 SERVICE_UI_ALWAYS，配置属性表可以仍显示如果 SERVICE_UI_ALLOWED 设置且_lpProps_参数中的属性值数组中没有有效的配置信息。</span><span class="sxs-lookup"><span data-stu-id="6e745-124">If SERVICE_UI_ALWAYS is not set, a configuration property sheet can still be displayed if SERVICE_UI_ALLOWED is set and valid configuration information is not available from the property value array in the  _lpProps_ parameter.</span></span> <span data-ttu-id="6e745-125">SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 必须为要显示的属性表。</span><span class="sxs-lookup"><span data-stu-id="6e745-125">Either SERVICE_UI_ALLOWED or SERVICE_UI_ALWAYS must be set for a property sheet to be displayed.</span></span> 
    
 <span data-ttu-id="6e745-126">_cValues_</span><span class="sxs-lookup"><span data-stu-id="6e745-126">_cValues_</span></span>
  
> <span data-ttu-id="6e745-127">[in]由_lpProps_指向[SPropValue](spropvalue.md)结构中的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="6e745-127">[in] The count of property values in the [SPropValue](spropvalue.md) structure pointed to by  _lpProps_.</span></span> 
    
 <span data-ttu-id="6e745-128">_lpProps_</span><span class="sxs-lookup"><span data-stu-id="6e745-128">_lpProps_</span></span>
  
> <span data-ttu-id="6e745-129">[in]一个指向介绍要在属性表中显示的属性的属性值的数组。</span><span class="sxs-lookup"><span data-stu-id="6e745-129">[in] A pointer to an array of property values that describe the properties to display in the property sheet.</span></span> <span data-ttu-id="6e745-130">如果邮件服务应配置的用户界面的情况下， _lpProps_参数不应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6e745-130">The  _lpProps_ parameter should not be NULL if the message service should be configured without a user interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="6e745-131">返回值</span><span class="sxs-lookup"><span data-stu-id="6e745-131">Return value</span></span>

<span data-ttu-id="6e745-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="6e745-132">S_OK</span></span> 
  
> <span data-ttu-id="6e745-133">已成功配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="6e745-133">The message service was successfully configured.</span></span>
    
<span data-ttu-id="6e745-134">MAPI_E_EXTENDED_ERROR</span><span class="sxs-lookup"><span data-stu-id="6e745-134">MAPI_E_EXTENDED_ERROR</span></span> 
  
> <span data-ttu-id="6e745-135">特定于邮件服务返回一个错误。</span><span class="sxs-lookup"><span data-stu-id="6e745-135">An error specific to a message service.</span></span> <span data-ttu-id="6e745-136">若要获取描述错误的[MAPIERROR](mapierror.md)结构，客户端应用程序应调用[IMsgServiceAdmin::GetLastError](imsgserviceadmin-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6e745-136">To get the [MAPIERROR](mapierror.md) structure that describes the error, the client application should call the [IMsgServiceAdmin::GetLastError](imsgserviceadmin-getlasterror.md) method.</span></span> 
    
<span data-ttu-id="6e745-137">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="6e745-137">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="6e745-138">所指的_lpUID_ **MAPIUID**不匹配的现有邮件服务。</span><span class="sxs-lookup"><span data-stu-id="6e745-138">The **MAPIUID** pointed to by  _lpUID_ does not match that of an existing message service.</span></span> 
    
<span data-ttu-id="6e745-139">MAPI_E_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="6e745-139">MAPI_E_NOT_INITIALIZED</span></span> 
  
> <span data-ttu-id="6e745-140">邮件服务没有入口点函数。</span><span class="sxs-lookup"><span data-stu-id="6e745-140">The message service does not have an entry point function.</span></span>
    
<span data-ttu-id="6e745-141">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="6e745-141">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="6e745-142">用户取消操作，通常通过单击属性表中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="6e745-142">The user canceled the operation, typically by clicking the **Cancel** button in the property sheet.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="6e745-143">说明</span><span class="sxs-lookup"><span data-stu-id="6e745-143">Remarks</span></span>

<span data-ttu-id="6e745-144">**IMsgServiceAdmin::ConfigureMsgService**方法使邮件服务能够使用或不配置属性表进行配置。</span><span class="sxs-lookup"><span data-stu-id="6e745-144">The **IMsgServiceAdmin::ConfigureMsgService** method enables a message service to be configured, with or without a configuration property sheet.</span></span> 
  
<span data-ttu-id="6e745-145">若要允许没有属性表显示配置，消息服务通常准备标头文件，其中包括所有必需的和可选属性以及它们的值的常量。</span><span class="sxs-lookup"><span data-stu-id="6e745-145">To allow configuration without a property sheet display, message services typically prepare a header file that includes constants for all the required and optional properties and their values.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="6e745-146">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="6e745-146">Notes to callers</span></span>

<span data-ttu-id="6e745-147">若要检索要配置的消息服务的**MAPIUID**结构，请从邮件服务表中的消息服务的行中检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列。</span><span class="sxs-lookup"><span data-stu-id="6e745-147">To retrieve the **MAPIUID** structure for the message service to configure, retrieve the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) column from the message service's row in the message service table.</span></span> <span data-ttu-id="6e745-148">有关详细信息，请参阅[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)方法中概述的过程。</span><span class="sxs-lookup"><span data-stu-id="6e745-148">For more information, see the procedure outlined in the [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) method.</span></span> 
  
<span data-ttu-id="6e745-149">您可以配置邮件服务，而不向用户显示属性表，仅当您具有要设置的属性值的高级信息。</span><span class="sxs-lookup"><span data-stu-id="6e745-149">You can configure a message service without displaying a property sheet to a user only if you have advance information about the property values to be set.</span></span> <span data-ttu-id="6e745-150">如果您要配置的消息服务，而不显示属性表、 _lpProps_参数中传递有效的属性值和未设置 MSG_SERVICE_UI_READ_ONLY，SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 的标志。</span><span class="sxs-lookup"><span data-stu-id="6e745-150">If you are configuring a message service without displaying a property sheet, pass valid property values in the  _lpProps_ parameter and do not set the MSG_SERVICE_UI_READ_ONLY, SERVICE_UI_ALLOWED, or SERVICE_UI_ALWAYS flags.</span></span> 
  
<span data-ttu-id="6e745-151">如果您收到来自用户通过属性表的全部或部分的配置信息，请在_ulFlags_中设置 SERVICE_UI_ALLOWED。</span><span class="sxs-lookup"><span data-stu-id="6e745-151">If you receive all or some of the configuration information from the user by way of a property sheet, set SERVICE_UI_ALLOWED in  _ulFlags_.</span></span> <span data-ttu-id="6e745-152">如果您使用现有的属性信息仅用于默认设置，并且用户能够更改的设置，请在_ulFlags_中设置 SERVICE_UI_ALWAYS。</span><span class="sxs-lookup"><span data-stu-id="6e745-152">If you use existing property information only to establish default settings and the user is able to change the settings, set SERVICE_UI_ALWAYS in  _ulFlags_.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6e745-153">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="6e745-153">MFCMAPI reference</span></span>

<span data-ttu-id="6e745-154">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6e745-154">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6e745-155">**文件**</span><span class="sxs-lookup"><span data-stu-id="6e745-155">**File**</span></span>|<span data-ttu-id="6e745-156">**函数**</span><span class="sxs-lookup"><span data-stu-id="6e745-156">**Function**</span></span>|<span data-ttu-id="6e745-157">**Comment**</span><span class="sxs-lookup"><span data-stu-id="6e745-157">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6e745-158">MAPIProfileFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="6e745-158">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="6e745-159">HrAddServiceToProfile</span><span class="sxs-lookup"><span data-stu-id="6e745-159">HrAddServiceToProfile</span></span>  <br/> |<span data-ttu-id="6e745-160">MFCMAPI 使用**IMsgServiceAdmin::ConfigureMsgService**方法配置已添加到一个配置文件服务。</span><span class="sxs-lookup"><span data-stu-id="6e745-160">MFCMAPI uses the **IMsgServiceAdmin::ConfigureMsgService** method to configure a service that has been added to a profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6e745-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e745-161">See also</span></span>



[<span data-ttu-id="6e745-162">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="6e745-162">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="6e745-163">SPropValue</span><span class="sxs-lookup"><span data-stu-id="6e745-163">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="6e745-164">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6e745-164">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="6e745-165">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6e745-165">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

