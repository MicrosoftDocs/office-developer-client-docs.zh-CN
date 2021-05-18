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
# <a name="imsgserviceadminconfiguremsgservice"></a><span data-ttu-id="18c84-103">IMsgServiceAdmin::ConfigureMsgService</span><span class="sxs-lookup"><span data-stu-id="18c84-103">IMsgServiceAdmin::ConfigureMsgService</span></span>

  
  
<span data-ttu-id="18c84-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="18c84-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="18c84-105">重新配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="18c84-105">Reconfigures a message service.</span></span>
  
```cpp
HRESULT ConfigureMsgService(
  LPMAPIUID lpUID,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG cValues,
  LPSPropValue lpProps
);
```

## <a name="parameters"></a><span data-ttu-id="18c84-106">参数</span><span class="sxs-lookup"><span data-stu-id="18c84-106">Parameters</span></span>

 <span data-ttu-id="18c84-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="18c84-107">_lpUID_</span></span>
  
> <span data-ttu-id="18c84-108">[in]指向 [MAPIUID](mapiuid.md) 结构的指针，其中包含要配置的邮件服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="18c84-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the message service to configure.</span></span> 
    
 <span data-ttu-id="18c84-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="18c84-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="18c84-110">[in]配置窗口的父窗口的属性表。</span><span class="sxs-lookup"><span data-stu-id="18c84-110">[in] A handle to the parent window of the configuration property sheet.</span></span>
    
 <span data-ttu-id="18c84-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="18c84-111">_ulFlags_</span></span>
  
> <span data-ttu-id="18c84-112">[in]控制屏幕显示的标志的位掩码属性表。</span><span class="sxs-lookup"><span data-stu-id="18c84-112">[in] A bitmask of flags that controls the display of the property sheet.</span></span> <span data-ttu-id="18c84-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="18c84-113">The following flags can be set:</span></span>
    
<span data-ttu-id="18c84-114">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="18c84-114">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="18c84-115">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="18c84-115">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="18c84-116">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="18c84-116">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="18c84-117">MSG_SERVICE_UI_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="18c84-117">MSG_SERVICE_UI_READ_ONLY</span></span> 
  
> <span data-ttu-id="18c84-118">邮件服务应显示其配置属性表但不允许用户更改它。</span><span class="sxs-lookup"><span data-stu-id="18c84-118">The message service should display its configuration property sheet but not enable the user to change it.</span></span> <span data-ttu-id="18c84-119">大多数邮件服务会忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="18c84-119">Most message services ignore this flag.</span></span>
    
<span data-ttu-id="18c84-120">SERVICE_UI_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="18c84-120">SERVICE_UI_ALLOWED</span></span> 
  
> <span data-ttu-id="18c84-121">邮件服务应仅在服务属性表配置时显示其配置。</span><span class="sxs-lookup"><span data-stu-id="18c84-121">The message service should display its configuration property sheet only if the service is not completely configured.</span></span>
    
<span data-ttu-id="18c84-122">SERVICE_UI_ALWAYS</span><span class="sxs-lookup"><span data-stu-id="18c84-122">SERVICE_UI_ALWAYS</span></span> 
  
> <span data-ttu-id="18c84-123">邮件服务必须始终显示其配置属性表。</span><span class="sxs-lookup"><span data-stu-id="18c84-123">The message service must always display its configuration property sheet.</span></span> <span data-ttu-id="18c84-124">如果未SERVICE_UI_ALWAYS，如果属性表设置 SERVICE_UI_ALLOWED，并且  _lpProps_ 参数中的属性值数组中未提供有效的配置信息，则仍可显示配置信息。</span><span class="sxs-lookup"><span data-stu-id="18c84-124">If SERVICE_UI_ALWAYS is not set, a configuration property sheet can still be displayed if SERVICE_UI_ALLOWED is set and valid configuration information is not available from the property value array in the  _lpProps_ parameter.</span></span> <span data-ttu-id="18c84-125">必须SERVICE_UI_ALLOWED或SERVICE_UI_ALWAYS设置选项，属性表显示内容。</span><span class="sxs-lookup"><span data-stu-id="18c84-125">Either SERVICE_UI_ALLOWED or SERVICE_UI_ALWAYS must be set for a property sheet to be displayed.</span></span> 
    
 <span data-ttu-id="18c84-126">_cValues_</span><span class="sxs-lookup"><span data-stu-id="18c84-126">_cValues_</span></span>
  
> <span data-ttu-id="18c84-127">[in] [SPropValue](spropvalue.md) 结构中由  _lpProps_ 指向的属性值计数。</span><span class="sxs-lookup"><span data-stu-id="18c84-127">[in] The count of property values in the [SPropValue](spropvalue.md) structure pointed to by  _lpProps_.</span></span> 
    
 <span data-ttu-id="18c84-128">_lpProps_</span><span class="sxs-lookup"><span data-stu-id="18c84-128">_lpProps_</span></span>
  
> <span data-ttu-id="18c84-129">[in]指向属性值数组的指针，这些属性值描述要显示在属性表。</span><span class="sxs-lookup"><span data-stu-id="18c84-129">[in] A pointer to an array of property values that describe the properties to display in the property sheet.</span></span> <span data-ttu-id="18c84-130">如果应在没有用户界面的情况下配置邮件服务，则  _lpProps_ 参数不应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="18c84-130">The  _lpProps_ parameter should not be NULL if the message service should be configured without a user interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="18c84-131">返回值</span><span class="sxs-lookup"><span data-stu-id="18c84-131">Return value</span></span>

<span data-ttu-id="18c84-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="18c84-132">S_OK</span></span> 
  
> <span data-ttu-id="18c84-133">已成功配置邮件服务。</span><span class="sxs-lookup"><span data-stu-id="18c84-133">The message service was successfully configured.</span></span>
    
<span data-ttu-id="18c84-134">MAPI_E_EXTENDED_ERROR</span><span class="sxs-lookup"><span data-stu-id="18c84-134">MAPI_E_EXTENDED_ERROR</span></span> 
  
> <span data-ttu-id="18c84-135">特定于邮件服务的错误。</span><span class="sxs-lookup"><span data-stu-id="18c84-135">An error specific to a message service.</span></span> <span data-ttu-id="18c84-136">若要获取描述错误的 [MAPIERROR](mapierror.md) 结构，客户端应用程序应调用 [IMsgServiceAdmin：：GetLastError](imsgserviceadmin-getlasterror.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="18c84-136">To get the [MAPIERROR](mapierror.md) structure that describes the error, the client application should call the [IMsgServiceAdmin::GetLastError](imsgserviceadmin-getlasterror.md) method.</span></span> 
    
<span data-ttu-id="18c84-137">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="18c84-137">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="18c84-138">_lpUID_ 指向的 **MAPIUID** 与现有邮件服务不匹配。</span><span class="sxs-lookup"><span data-stu-id="18c84-138">The **MAPIUID** pointed to by  _lpUID_ does not match that of an existing message service.</span></span> 
    
<span data-ttu-id="18c84-139">MAPI_E_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="18c84-139">MAPI_E_NOT_INITIALIZED</span></span> 
  
> <span data-ttu-id="18c84-140">邮件服务没有入口点功能。</span><span class="sxs-lookup"><span data-stu-id="18c84-140">The message service does not have an entry point function.</span></span>
    
<span data-ttu-id="18c84-141">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="18c84-141">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="18c84-142">用户通常通过单击"取消"按钮来取消属性表。 </span><span class="sxs-lookup"><span data-stu-id="18c84-142">The user canceled the operation, typically by clicking the **Cancel** button in the property sheet.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="18c84-143">备注</span><span class="sxs-lookup"><span data-stu-id="18c84-143">Remarks</span></span>

<span data-ttu-id="18c84-144">**IMsgServiceAdmin：：ConfigureMsgService** 方法使邮件服务可以配置，也可以不配置属性表。</span><span class="sxs-lookup"><span data-stu-id="18c84-144">The **IMsgServiceAdmin::ConfigureMsgService** method enables a message service to be configured, with or without a configuration property sheet.</span></span> 
  
<span data-ttu-id="18c84-145">为了允许在不显示属性表配置，邮件服务通常会准备一个头文件，其中包含所有必需和可选属性及其值的常量。</span><span class="sxs-lookup"><span data-stu-id="18c84-145">To allow configuration without a property sheet display, message services typically prepare a header file that includes constants for all the required and optional properties and their values.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="18c84-146">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="18c84-146">Notes to callers</span></span>

<span data-ttu-id="18c84-147">若要检索要配置的邮件服务的 **MAPIUID** 结构，请从邮件服务表中邮件服务的行中检索 **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列。</span><span class="sxs-lookup"><span data-stu-id="18c84-147">To retrieve the **MAPIUID** structure for the message service to configure, retrieve the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) column from the message service's row in the message service table.</span></span> <span data-ttu-id="18c84-148">有关详细信息，请参阅 [IMsgServiceAdmin：：CreateMsgService 方法中概述](imsgserviceadmin-createmsgservice.md) 的过程。</span><span class="sxs-lookup"><span data-stu-id="18c84-148">For more information, see the procedure outlined in the [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) method.</span></span> 
  
<span data-ttu-id="18c84-149">只有在有要设置的属性值的预先信息属性表，才能配置邮件服务，而不向用户显示通知。</span><span class="sxs-lookup"><span data-stu-id="18c84-149">You can configure a message service without displaying a property sheet to a user only if you have advance information about the property values to be set.</span></span> <span data-ttu-id="18c84-150">如果要配置邮件服务而不显示 属性表，请传递  _lpProps_ 参数中的有效属性值，并且不要设置 MSG_SERVICE_UI_READ_ONLY、SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 标志。</span><span class="sxs-lookup"><span data-stu-id="18c84-150">If you are configuring a message service without displaying a property sheet, pass valid property values in the  _lpProps_ parameter and do not set the MSG_SERVICE_UI_READ_ONLY, SERVICE_UI_ALLOWED, or SERVICE_UI_ALWAYS flags.</span></span> 
  
<span data-ttu-id="18c84-151">如果您通过安装方法从用户收到所有或部分配置信息，属性表  _ulFlags_ SERVICE_UI_ALLOWED设置配置信息。</span><span class="sxs-lookup"><span data-stu-id="18c84-151">If you receive all or some of the configuration information from the user by way of a property sheet, set SERVICE_UI_ALLOWED in  _ulFlags_.</span></span> <span data-ttu-id="18c84-152">如果您使用现有属性信息来建立默认设置，并且用户能够更改设置，则SERVICE_UI_ALWAYS  _ulFlags_ 中。</span><span class="sxs-lookup"><span data-stu-id="18c84-152">If you use existing property information only to establish default settings and the user is able to change the settings, set SERVICE_UI_ALWAYS in  _ulFlags_.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="18c84-153">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="18c84-153">MFCMAPI reference</span></span>

<span data-ttu-id="18c84-154">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="18c84-154">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="18c84-155">**文件**</span><span class="sxs-lookup"><span data-stu-id="18c84-155">**File**</span></span>|<span data-ttu-id="18c84-156">**函数**</span><span class="sxs-lookup"><span data-stu-id="18c84-156">**Function**</span></span>|<span data-ttu-id="18c84-157">**备注**</span><span class="sxs-lookup"><span data-stu-id="18c84-157">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="18c84-158">MAPIProfileFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="18c84-158">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="18c84-159">HrAddServiceToProfile</span><span class="sxs-lookup"><span data-stu-id="18c84-159">HrAddServiceToProfile</span></span>  <br/> |<span data-ttu-id="18c84-160">MFCMAPI 使用 **IMsgServiceAdmin：：ConfigureMsgService** 方法配置已添加到配置文件的服务。</span><span class="sxs-lookup"><span data-stu-id="18c84-160">MFCMAPI uses the **IMsgServiceAdmin::ConfigureMsgService** method to configure a service that has been added to a profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="18c84-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18c84-161">See also</span></span>



[<span data-ttu-id="18c84-162">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="18c84-162">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="18c84-163">SPropValue</span><span class="sxs-lookup"><span data-stu-id="18c84-163">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="18c84-164">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="18c84-164">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="18c84-165">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="18c84-165">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

