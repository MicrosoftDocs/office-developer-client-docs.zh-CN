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
ms.openlocfilehash: 87ac394f9ab77b092cdfcd44f65b040a039319e7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422185"
---
# <a name="imsgserviceadminconfiguremsgservice"></a><span data-ttu-id="94d2a-103">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="94d2a-103">IMsgServiceAdmin::ConfigureMsgService</span></span>

  
  
<span data-ttu-id="94d2a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="94d2a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="94d2a-105">重新配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="94d2a-105">Reconfigures a message service.</span></span>
  
```cpp
HRESULT ConfigureMsgService(
  LPMAPIUID lpUID,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG cValues,
  LPSPropValue lpProps
);
```

## <a name="parameters"></a><span data-ttu-id="94d2a-106">参数</span><span class="sxs-lookup"><span data-stu-id="94d2a-106">Parameters</span></span>

 <span data-ttu-id="94d2a-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="94d2a-107">_lpUID_</span></span>
  
> <span data-ttu-id="94d2a-108">实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含要配置的邮件服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="94d2a-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the message service to configure.</span></span> 
    
 <span data-ttu-id="94d2a-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="94d2a-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="94d2a-110">实时配置属性表的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="94d2a-110">[in] A handle to the parent window of the configuration property sheet.</span></span>
    
 <span data-ttu-id="94d2a-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="94d2a-111">_ulFlags_</span></span>
  
> <span data-ttu-id="94d2a-112">实时用于控制属性表的显示的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="94d2a-112">[in] A bitmask of flags that controls the display of the property sheet.</span></span> <span data-ttu-id="94d2a-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="94d2a-113">The following flags can be set:</span></span>
    
<span data-ttu-id="94d2a-114">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="94d2a-114">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="94d2a-115">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="94d2a-115">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="94d2a-116">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="94d2a-116">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="94d2a-117">MSG_SERVICE_UI_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="94d2a-117">MSG_SERVICE_UI_READ_ONLY</span></span> 
  
> <span data-ttu-id="94d2a-118">邮件服务应显示其配置属性表, 但不允许用户对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="94d2a-118">The message service should display its configuration property sheet but not enable the user to change it.</span></span> <span data-ttu-id="94d2a-119">大多数邮件服务都会忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="94d2a-119">Most message services ignore this flag.</span></span>
    
<span data-ttu-id="94d2a-120">SERVICE_UI_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="94d2a-120">SERVICE_UI_ALLOWED</span></span> 
  
> <span data-ttu-id="94d2a-121">仅当未完全配置服务时, 邮件服务才应显示其配置属性表。</span><span class="sxs-lookup"><span data-stu-id="94d2a-121">The message service should display its configuration property sheet only if the service is not completely configured.</span></span>
    
<span data-ttu-id="94d2a-122">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="94d2a-122">SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="94d2a-123">邮件服务必须始终显示其 "配置" 属性表。</span><span class="sxs-lookup"><span data-stu-id="94d2a-123">The message service must always display its configuration property sheet.</span></span> <span data-ttu-id="94d2a-124">如果未设置 SERVICE_UI_ALWAYS, 则在设置 SERVICE_UI_ALLOWED 并在_lpProps_参数的属性值数组中不提供有效的配置信息时, 仍可以显示配置属性表。</span><span class="sxs-lookup"><span data-stu-id="94d2a-124">If SERVICE_UI_ALWAYS is not set, a configuration property sheet can still be displayed if SERVICE_UI_ALLOWED is set and valid configuration information is not available from the property value array in the  _lpProps_ parameter.</span></span> <span data-ttu-id="94d2a-125">必须设置 SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS, 才能显示属性表。</span><span class="sxs-lookup"><span data-stu-id="94d2a-125">Either SERVICE_UI_ALLOWED or SERVICE_UI_ALWAYS must be set for a property sheet to be displayed.</span></span> 
    
 <span data-ttu-id="94d2a-126">_cValues_</span><span class="sxs-lookup"><span data-stu-id="94d2a-126">_cValues_</span></span>
  
> <span data-ttu-id="94d2a-127">实时由_lpProps_指向的[SPropValue](spropvalue.md)结构中的属性值的计数。</span><span class="sxs-lookup"><span data-stu-id="94d2a-127">[in] The count of property values in the [SPropValue](spropvalue.md) structure pointed to by  _lpProps_.</span></span> 
    
 <span data-ttu-id="94d2a-128">_lpProps_</span><span class="sxs-lookup"><span data-stu-id="94d2a-128">_lpProps_</span></span>
  
> <span data-ttu-id="94d2a-129">实时指向描述要在属性表中显示的属性的属性值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="94d2a-129">[in] A pointer to an array of property values that describe the properties to display in the property sheet.</span></span> <span data-ttu-id="94d2a-130">如果应在不使用用户界面的情况下配置邮件服务, 则_lpProps_参数不应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="94d2a-130">The  _lpProps_ parameter should not be NULL if the message service should be configured without a user interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="94d2a-131">返回值</span><span class="sxs-lookup"><span data-stu-id="94d2a-131">Return value</span></span>

<span data-ttu-id="94d2a-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="94d2a-132">S_OK</span></span> 
  
> <span data-ttu-id="94d2a-133">邮件服务已成功配置。</span><span class="sxs-lookup"><span data-stu-id="94d2a-133">The message service was successfully configured.</span></span>
    
<span data-ttu-id="94d2a-134">MAPI_E_EXTENDED_ERROR</span><span class="sxs-lookup"><span data-stu-id="94d2a-134">MAPI_E_EXTENDED_ERROR</span></span> 
  
> <span data-ttu-id="94d2a-135">特定于邮件服务的错误。</span><span class="sxs-lookup"><span data-stu-id="94d2a-135">An error specific to a message service.</span></span> <span data-ttu-id="94d2a-136">若要获取描述错误的[MAPIERROR](mapierror.md)结构, 客户端应用程序应调用[IMsgServiceAdmin:: GetLastError](imsgserviceadmin-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="94d2a-136">To get the [MAPIERROR](mapierror.md) structure that describes the error, the client application should call the [IMsgServiceAdmin::GetLastError](imsgserviceadmin-getlasterror.md) method.</span></span> 
    
<span data-ttu-id="94d2a-137">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="94d2a-137">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="94d2a-138">lpUID 指向的**MAPIUID**与现有邮件服务的__ 不匹配。</span><span class="sxs-lookup"><span data-stu-id="94d2a-138">The **MAPIUID** pointed to by  _lpUID_ does not match that of an existing message service.</span></span> 
    
<span data-ttu-id="94d2a-139">MAPI_E_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="94d2a-139">MAPI_E_NOT_INITIALIZED</span></span> 
  
> <span data-ttu-id="94d2a-140">邮件服务没有入口点函数。</span><span class="sxs-lookup"><span data-stu-id="94d2a-140">The message service does not have an entry point function.</span></span>
    
<span data-ttu-id="94d2a-141">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="94d2a-141">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="94d2a-142">用户取消了操作, 通常是单击属性表中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="94d2a-142">The user canceled the operation, typically by clicking the **Cancel** button in the property sheet.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="94d2a-143">说明</span><span class="sxs-lookup"><span data-stu-id="94d2a-143">Remarks</span></span>

<span data-ttu-id="94d2a-144">**IMsgServiceAdmin:: ConfigureMsgService**方法允许使用或不使用配置属性表来配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="94d2a-144">The **IMsgServiceAdmin::ConfigureMsgService** method enables a message service to be configured, with or without a configuration property sheet.</span></span> 
  
<span data-ttu-id="94d2a-145">若要允许在不显示属性表的情况下进行配置, 邮件服务通常准备一个头文件, 其中包含所有必需属性和可选属性及其值的常量。</span><span class="sxs-lookup"><span data-stu-id="94d2a-145">To allow configuration without a property sheet display, message services typically prepare a header file that includes constants for all the required and optional properties and their values.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="94d2a-146">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="94d2a-146">Notes to callers</span></span>

<span data-ttu-id="94d2a-147">若要检索要配置的邮件服务的**MAPIUID**结构, 请从邮件服务表中的邮件服务行检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列。</span><span class="sxs-lookup"><span data-stu-id="94d2a-147">To retrieve the **MAPIUID** structure for the message service to configure, retrieve the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) column from the message service's row in the message service table.</span></span> <span data-ttu-id="94d2a-148">有关详细信息, 请参阅[IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md)方法中概述的过程。</span><span class="sxs-lookup"><span data-stu-id="94d2a-148">For more information, see the procedure outlined in the [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) method.</span></span> 
  
<span data-ttu-id="94d2a-149">只有在您具有有关要设置的属性值的高级信息的情况下, 才能将邮件服务配置为不向用户显示属性表。</span><span class="sxs-lookup"><span data-stu-id="94d2a-149">You can configure a message service without displaying a property sheet to a user only if you have advance information about the property values to be set.</span></span> <span data-ttu-id="94d2a-150">如果要配置邮件服务而不显示属性表, 请在_lpProps_参数中传递有效的属性值, 不要设置 MSG_SERVICE_UI_READ_ONLY、SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 标志。</span><span class="sxs-lookup"><span data-stu-id="94d2a-150">If you are configuring a message service without displaying a property sheet, pass valid property values in the  _lpProps_ parameter and do not set the MSG_SERVICE_UI_READ_ONLY, SERVICE_UI_ALLOWED, or SERVICE_UI_ALWAYS flags.</span></span> 
  
<span data-ttu-id="94d2a-151">如果通过属性表从用户处接收全部或部分配置信息, 请在_ulFlags_中设置 SERVICE_UI_ALLOWED。</span><span class="sxs-lookup"><span data-stu-id="94d2a-151">If you receive all or some of the configuration information from the user by way of a property sheet, set SERVICE_UI_ALLOWED in  _ulFlags_.</span></span> <span data-ttu-id="94d2a-152">如果您仅使用现有属性信息来建立默认设置, 并且用户能够更改设置, 请在_ulFlags_中设置 SERVICE_UI_ALWAYS。</span><span class="sxs-lookup"><span data-stu-id="94d2a-152">If you use existing property information only to establish default settings and the user is able to change the settings, set SERVICE_UI_ALWAYS in  _ulFlags_.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="94d2a-153">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="94d2a-153">MFCMAPI reference</span></span>

<span data-ttu-id="94d2a-154">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="94d2a-154">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="94d2a-155">**文件**</span><span class="sxs-lookup"><span data-stu-id="94d2a-155">**File**</span></span>|<span data-ttu-id="94d2a-156">**函数**</span><span class="sxs-lookup"><span data-stu-id="94d2a-156">**Function**</span></span>|<span data-ttu-id="94d2a-157">**备注**</span><span class="sxs-lookup"><span data-stu-id="94d2a-157">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="94d2a-158">MAPIProfileFunctions</span><span class="sxs-lookup"><span data-stu-id="94d2a-158">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="94d2a-159">HrAddServiceToProfile</span><span class="sxs-lookup"><span data-stu-id="94d2a-159">HrAddServiceToProfile</span></span>  <br/> |<span data-ttu-id="94d2a-160">MFCMAPI 使用**IMsgServiceAdmin:: ConfigureMsgService**方法配置已添加到配置文件中的服务。</span><span class="sxs-lookup"><span data-stu-id="94d2a-160">MFCMAPI uses the **IMsgServiceAdmin::ConfigureMsgService** method to configure a service that has been added to a profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="94d2a-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94d2a-161">See also</span></span>



[<span data-ttu-id="94d2a-162">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="94d2a-162">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="94d2a-163">SPropValue</span><span class="sxs-lookup"><span data-stu-id="94d2a-163">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="94d2a-164">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="94d2a-164">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="94d2a-165">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="94d2a-165">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

