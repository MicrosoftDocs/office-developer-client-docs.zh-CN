---
title: IMsgServiceAdminDeleteMsgService
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.DeleteMsgService
api_type:
- COM
ms.assetid: 3a6b34eb-9d46-488f-8d02-91b27c35de67
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cef03e33abab81a407698b73a007f247ef88194
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309987"
---
# <a name="imsgserviceadmindeletemsgservice"></a><span data-ttu-id="a0d83-103">IMsgServiceAdmin::DeleteMsgService</span><span class="sxs-lookup"><span data-stu-id="a0d83-103">IMsgServiceAdmin::DeleteMsgService</span></span>

  
  
<span data-ttu-id="a0d83-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a0d83-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a0d83-105">从配置文件中删除邮件服务。</span><span class="sxs-lookup"><span data-stu-id="a0d83-105">Deletes a message service from a profile.</span></span>
  
```cpp
HRESULT DeleteMsgService(
  LPMAPIUID lpuid
);
```

## <a name="parameters"></a><span data-ttu-id="a0d83-106">参数</span><span class="sxs-lookup"><span data-stu-id="a0d83-106">Parameters</span></span>

 <span data-ttu-id="a0d83-107">_lpuid_</span><span class="sxs-lookup"><span data-stu-id="a0d83-107">_lpuid_</span></span>
  
> <span data-ttu-id="a0d83-108">实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含要删除的邮件服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a0d83-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the message service to delete.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a0d83-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a0d83-109">Return value</span></span>

<span data-ttu-id="a0d83-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0d83-110">S_OK</span></span> 
  
> <span data-ttu-id="a0d83-111">邮件服务已被删除。</span><span class="sxs-lookup"><span data-stu-id="a0d83-111">The message service was deleted.</span></span>
    
<span data-ttu-id="a0d83-112">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="a0d83-112">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="a0d83-113">_lpuid_指向的**MAPIUID**与现有的邮件服务不匹配。</span><span class="sxs-lookup"><span data-stu-id="a0d83-113">The **MAPIUID** pointed to by  _lpuid_ does not match an existing message service.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a0d83-114">注解</span><span class="sxs-lookup"><span data-stu-id="a0d83-114">Remarks</span></span>

<span data-ttu-id="a0d83-115">**IMsgServiceAdmin::D eletemsgservice**方法从配置文件中删除邮件服务。</span><span class="sxs-lookup"><span data-stu-id="a0d83-115">The **IMsgServiceAdmin::DeleteMsgService** method deletes a message service from a profile.</span></span> <span data-ttu-id="a0d83-116">**DeleteMsgService**删除与邮件服务相关的所有配置文件节。</span><span class="sxs-lookup"><span data-stu-id="a0d83-116">**DeleteMsgService** removes all profile sections related to the message service.</span></span> 
  
 <span data-ttu-id="a0d83-117">**DeleteMsgService**执行以下步骤以删除邮件服务:</span><span class="sxs-lookup"><span data-stu-id="a0d83-117">**DeleteMsgService** performs the following steps to delete the message service:</span></span> 
  
1. <span data-ttu-id="a0d83-118">调用邮件服务的入口点函数, 并将_ulContext_参数设置为 MSG_SERVICE_DELETE, 然后再删除配置文件节。</span><span class="sxs-lookup"><span data-stu-id="a0d83-118">Calls the message service's entry point function with the  _ulContext_ parameter set to MSG_SERVICE_DELETE before the profile sections are removed.</span></span> <span data-ttu-id="a0d83-119">这允许服务执行任何特定于服务的任务。</span><span class="sxs-lookup"><span data-stu-id="a0d83-119">This allows the service to perform any service-specific tasks.</span></span> 
    
2. <span data-ttu-id="a0d83-120">删除邮件服务。</span><span class="sxs-lookup"><span data-stu-id="a0d83-120">Deletes the message service.</span></span>
    
3. <span data-ttu-id="a0d83-121">删除邮件服务的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="a0d83-121">Deletes the message service's profile section.</span></span>
    
<span data-ttu-id="a0d83-122">删除服务后, 不会再次调用邮件服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="a0d83-122">The message service's entry point function is not called again after the service has been deleted.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="a0d83-123">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a0d83-123">Notes to callers</span></span>

<span data-ttu-id="a0d83-124">若要检索要删除的邮件服务的**MAPIUID**结构, 请从邮件服务表中的邮件服务行检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性列。</span><span class="sxs-lookup"><span data-stu-id="a0d83-124">To retrieve the **MAPIUID** structure for the message service to delete, retrieve the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property column from the message service's row in the message service table.</span></span> <span data-ttu-id="a0d83-125">有关详细信息, 请参阅[IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md)方法中概述的过程。</span><span class="sxs-lookup"><span data-stu-id="a0d83-125">For more information, see the procedure outlined in the [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a0d83-126">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a0d83-126">MFCMAPI reference</span></span>

<span data-ttu-id="a0d83-127">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a0d83-127">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a0d83-128">**文件**</span><span class="sxs-lookup"><span data-stu-id="a0d83-128">**File**</span></span>|<span data-ttu-id="a0d83-129">**函数**</span><span class="sxs-lookup"><span data-stu-id="a0d83-129">**Function**</span></span>|<span data-ttu-id="a0d83-130">**备注**</span><span class="sxs-lookup"><span data-stu-id="a0d83-130">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a0d83-131">MsgServiceTableDlg</span><span class="sxs-lookup"><span data-stu-id="a0d83-131">MsgServiceTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="a0d83-132">CMsgServiceTableDlg:: OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="a0d83-132">CMsgServiceTableDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="a0d83-133">MFCMAPI 使用**IMsgServiceAdmin::D eletemsgservice**方法删除选定的服务。</span><span class="sxs-lookup"><span data-stu-id="a0d83-133">MFCMAPI uses the **IMsgServiceAdmin::DeleteMsgService** method to delete the selected service.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a0d83-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0d83-134">See also</span></span>



[<span data-ttu-id="a0d83-135">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="a0d83-135">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="a0d83-136">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a0d83-136">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="a0d83-137">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a0d83-137">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

