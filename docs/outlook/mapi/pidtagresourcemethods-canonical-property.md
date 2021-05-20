---
title: PidTagResourceMethods 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResourceMethods
api_type:
- COM
ms.assetid: 60ebbcd5-b758-4c96-b8ec-089e0aae1a5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e9aee3280edbed60e97ef6e00e61f3086f6f07ce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436333"
---
# <a name="pidtagresourcemethods-canonical-property"></a><span data-ttu-id="90239-103">PidTagResourceMethods 规范属性</span><span class="sxs-lookup"><span data-stu-id="90239-103">PidTagResourceMethods Canonical Property</span></span>

  
  
<span data-ttu-id="90239-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="90239-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="90239-105">包含指示 **IMAPIStatus** 接口中 status 对象支持的方法的位掩码标志。</span><span class="sxs-lookup"><span data-stu-id="90239-105">Contains a bitmask of flags that indicate the methods in the **IMAPIStatus** interface that are supported by the status object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="90239-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="90239-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="90239-107">PR_RESOURCE_METHODS</span><span class="sxs-lookup"><span data-stu-id="90239-107">PR_RESOURCE_METHODS</span></span>  <br/> |
|<span data-ttu-id="90239-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="90239-108">Identifier:</span></span>  <br/> |<span data-ttu-id="90239-109">0x3E02</span><span class="sxs-lookup"><span data-stu-id="90239-109">0x3E02</span></span>  <br/> |
|<span data-ttu-id="90239-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="90239-110">Data type:</span></span>  <br/> |<span data-ttu-id="90239-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="90239-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="90239-112">区域：</span><span class="sxs-lookup"><span data-stu-id="90239-112">Area:</span></span>  <br/> |<span data-ttu-id="90239-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="90239-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="90239-114">备注</span><span class="sxs-lookup"><span data-stu-id="90239-114">Remarks</span></span>

<span data-ttu-id="90239-115">此属性指示状态对象的 **IMAPIStatus** 实现中支持哪些方法。</span><span class="sxs-lookup"><span data-stu-id="90239-115">This property indicates which of the methods in a status object's implementation of **IMAPIStatus** are supported.</span></span> <span data-ttu-id="90239-116">Status 对象允许从不受MAPI_E_NO_SUPPORT返回值。</span><span class="sxs-lookup"><span data-stu-id="90239-116">Status objects are allowed to return MAPI_E_NO_SUPPORT from unsupported methods.</span></span> 
  
<span data-ttu-id="90239-117">客户端使用 status 对象的 **PR_RESOURCE_METHODS** 属性，以避免调用不受支持的方法。</span><span class="sxs-lookup"><span data-stu-id="90239-117">Clients use a status object's **PR_RESOURCE_METHODS** property to avoid making calls to unsupported methods.</span></span> <span data-ttu-id="90239-118">如果设置了与特定方法对应的标志，则该方法存在并可以调用。</span><span class="sxs-lookup"><span data-stu-id="90239-118">If the flag that corresponds to a particular method is set, the method exists and can be called.</span></span> <span data-ttu-id="90239-119">如果该标志是明确的，则不应调用 该方法。</span><span class="sxs-lookup"><span data-stu-id="90239-119">If that flag is clear, the method should not be called.</span></span> 
  
<span data-ttu-id="90239-120">MAPI 实现的状态对象支持以下方法：</span><span class="sxs-lookup"><span data-stu-id="90239-120">The status objects implemented by MAPI support the following methods:</span></span>
  
|<span data-ttu-id="90239-121">**Status 对象**</span><span class="sxs-lookup"><span data-stu-id="90239-121">**Status object**</span></span>|<span data-ttu-id="90239-122">**支持的方法**</span><span class="sxs-lookup"><span data-stu-id="90239-122">**Supported methods**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90239-123">MAPI 子系统</span><span class="sxs-lookup"><span data-stu-id="90239-123">MAPI subsystem</span></span>  <br/> |<span data-ttu-id="90239-124">**仅 ValidateState**</span><span class="sxs-lookup"><span data-stu-id="90239-124">**ValidateState** only</span></span>  <br/> |
|<span data-ttu-id="90239-125">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="90239-125">MAPI address book</span></span>  <br/> |<span data-ttu-id="90239-126">**仅 ValidateState**</span><span class="sxs-lookup"><span data-stu-id="90239-126">**ValidateState** only</span></span>  <br/> |
|<span data-ttu-id="90239-127">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="90239-127">MAPI spooler</span></span>  <br/> |<span data-ttu-id="90239-128">**ValidateState** 和 **FlushQueues**</span><span class="sxs-lookup"><span data-stu-id="90239-128">**ValidateState** and **FlushQueues**</span></span> <br/> |
   
<span data-ttu-id="90239-129">可以在以下值中设置以下一个或多个 **PR_RESOURCE_METHODS：**</span><span class="sxs-lookup"><span data-stu-id="90239-129">One or more of the following flags can be set in **PR_RESOURCE_METHODS**:</span></span>
  
<span data-ttu-id="90239-130">STATUS_CHANGE_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="90239-130">STATUS_CHANGE_PASSWORD</span></span> 
  
> <span data-ttu-id="90239-131">指示 [IMAPIStatus：：ChangePassword](imapistatus-changepassword.md) 方法受支持。</span><span class="sxs-lookup"><span data-stu-id="90239-131">Indicates that the [IMAPIStatus::ChangePassword](imapistatus-changepassword.md) method is supported.</span></span> 
    
<span data-ttu-id="90239-132">STATUS_FLUSH_QUEUES</span><span class="sxs-lookup"><span data-stu-id="90239-132">STATUS_FLUSH_QUEUES</span></span> 
  
> <span data-ttu-id="90239-133">指示 [IMAPIStatus：：FlushQueues](imapistatus-flushqueues.md) 方法受支持。</span><span class="sxs-lookup"><span data-stu-id="90239-133">Indicates that the [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method is supported.</span></span> 
    
<span data-ttu-id="90239-134">STATUS_SETTINGS_DIALOG</span><span class="sxs-lookup"><span data-stu-id="90239-134">STATUS_SETTINGS_DIALOG</span></span> 
  
> <span data-ttu-id="90239-135">指示 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 方法受支持。</span><span class="sxs-lookup"><span data-stu-id="90239-135">Indicates that the [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method is supported.</span></span> 
    
<span data-ttu-id="90239-136">STATUS_VALIDATE_STATE</span><span class="sxs-lookup"><span data-stu-id="90239-136">STATUS_VALIDATE_STATE</span></span> 
  
> <span data-ttu-id="90239-137">指示 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法受支持。</span><span class="sxs-lookup"><span data-stu-id="90239-137">Indicates that the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method is supported.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="90239-138">相关资源</span><span class="sxs-lookup"><span data-stu-id="90239-138">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="90239-139">头文件</span><span class="sxs-lookup"><span data-stu-id="90239-139">Header files</span></span>

<span data-ttu-id="90239-140">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="90239-140">Mapidefs.h</span></span>
  
> <span data-ttu-id="90239-141">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="90239-141">Provides data type definitions.</span></span>
    
<span data-ttu-id="90239-142">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="90239-142">Mapitags.h</span></span>
  
> <span data-ttu-id="90239-143">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="90239-143">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="90239-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90239-144">See also</span></span>



[<span data-ttu-id="90239-145">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="90239-145">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="90239-146">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="90239-146">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="90239-147">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="90239-147">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="90239-148">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="90239-148">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

