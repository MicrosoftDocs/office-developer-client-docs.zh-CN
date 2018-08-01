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
ms.openlocfilehash: 0a3021ed386aa00777694452a755693fc4078093
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775836"
---
# <a name="imsgserviceadmindeletemsgservice"></a><span data-ttu-id="023f2-103">IMsgServiceAdmin::DeleteMsgService</span><span class="sxs-lookup"><span data-stu-id="023f2-103">IMsgServiceAdmin::DeleteMsgService</span></span>

  
  
<span data-ttu-id="023f2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="023f2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="023f2-105">从配置文件中删除的消息服务。</span><span class="sxs-lookup"><span data-stu-id="023f2-105">Deletes a message service from a profile.</span></span>
  
```cpp
HRESULT DeleteMsgService(
  LPMAPIUID lpuid
);
```

## <a name="parameters"></a><span data-ttu-id="023f2-106">参数</span><span class="sxs-lookup"><span data-stu-id="023f2-106">Parameters</span></span>

 <span data-ttu-id="023f2-107">_lpuid_</span><span class="sxs-lookup"><span data-stu-id="023f2-107">_lpuid_</span></span>
  
> <span data-ttu-id="023f2-108">[in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要删除的消息服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="023f2-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the message service to delete.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="023f2-109">返回值</span><span class="sxs-lookup"><span data-stu-id="023f2-109">Return value</span></span>

<span data-ttu-id="023f2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="023f2-110">S_OK</span></span> 
  
> <span data-ttu-id="023f2-111">已删除邮件服务。</span><span class="sxs-lookup"><span data-stu-id="023f2-111">The message service was deleted.</span></span>
    
<span data-ttu-id="023f2-112">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="023f2-112">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="023f2-113">指向_lpuid_ **MAPIUID**与现有邮件服务不匹配。</span><span class="sxs-lookup"><span data-stu-id="023f2-113">The **MAPIUID** pointed to by  _lpuid_ does not match an existing message service.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="023f2-114">说明</span><span class="sxs-lookup"><span data-stu-id="023f2-114">Remarks</span></span>

<span data-ttu-id="023f2-115">**IMsgServiceAdmin::DeleteMsgService**方法从一个配置文件中删除的消息服务。</span><span class="sxs-lookup"><span data-stu-id="023f2-115">The **IMsgServiceAdmin::DeleteMsgService** method deletes a message service from a profile.</span></span> <span data-ttu-id="023f2-116">**DeleteMsgService**删除所有与邮件服务相关的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="023f2-116">**DeleteMsgService** removes all profile sections related to the message service.</span></span> 
  
 <span data-ttu-id="023f2-117">**DeleteMsgService**执行以下步骤删除消息服务：</span><span class="sxs-lookup"><span data-stu-id="023f2-117">**DeleteMsgService** performs the following steps to delete the message service:</span></span> 
  
1. <span data-ttu-id="023f2-118">与之前删除的配置文件部分设置为 MSG_SERVICE_DELETE _ulContext_参数调用消息服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="023f2-118">Calls the message service's entry point function with the  _ulContext_ parameter set to MSG_SERVICE_DELETE before the profile sections are removed.</span></span> <span data-ttu-id="023f2-119">这样，该服务以执行任何特定于服务的任务。</span><span class="sxs-lookup"><span data-stu-id="023f2-119">This allows the service to perform any service-specific tasks.</span></span> 
    
2. <span data-ttu-id="023f2-120">删除邮件服务。</span><span class="sxs-lookup"><span data-stu-id="023f2-120">Deletes the message service.</span></span>
    
3. <span data-ttu-id="023f2-121">删除消息服务的配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="023f2-121">Deletes the message service's profile section.</span></span>
    
<span data-ttu-id="023f2-122">删除服务后消息服务的入口点函数不再次调用。</span><span class="sxs-lookup"><span data-stu-id="023f2-122">The message service's entry point function is not called again after the service has been deleted.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="023f2-123">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="023f2-123">Notes to callers</span></span>

<span data-ttu-id="023f2-124">若要检索要删除的消息服务的**MAPIUID**结构，请从邮件服务表中的消息服务的行中检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性列。</span><span class="sxs-lookup"><span data-stu-id="023f2-124">To retrieve the **MAPIUID** structure for the message service to delete, retrieve the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property column from the message service's row in the message service table.</span></span> <span data-ttu-id="023f2-125">有关详细信息，请参阅[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)方法中概述的过程。</span><span class="sxs-lookup"><span data-stu-id="023f2-125">For more information, see the procedure outlined in the [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="023f2-126">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="023f2-126">MFCMAPI reference</span></span>

<span data-ttu-id="023f2-127">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="023f2-127">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="023f2-128">**文件**</span><span class="sxs-lookup"><span data-stu-id="023f2-128">**File**</span></span>|<span data-ttu-id="023f2-129">**函数**</span><span class="sxs-lookup"><span data-stu-id="023f2-129">**Function**</span></span>|<span data-ttu-id="023f2-130">**Comment**</span><span class="sxs-lookup"><span data-stu-id="023f2-130">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="023f2-131">MsgServiceTableDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="023f2-131">MsgServiceTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="023f2-132">CMsgServiceTableDlg::OnDeleteSelectedItem</span><span class="sxs-lookup"><span data-stu-id="023f2-132">CMsgServiceTableDlg::OnDeleteSelectedItem</span></span>  <br/> |<span data-ttu-id="023f2-133">MFCMAPI 使用**IMsgServiceAdmin::DeleteMsgService**方法删除选定的服务。</span><span class="sxs-lookup"><span data-stu-id="023f2-133">MFCMAPI uses the **IMsgServiceAdmin::DeleteMsgService** method to delete the selected service.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="023f2-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="023f2-134">See also</span></span>



[<span data-ttu-id="023f2-135">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="023f2-135">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="023f2-136">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="023f2-136">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="023f2-137">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="023f2-137">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

