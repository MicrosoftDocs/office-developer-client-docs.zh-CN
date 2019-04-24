---
title: IProfAdminDeleteProfile
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.DeleteProfile
api_type:
- COM
ms.assetid: 730af2da-4c4a-42a7-9d52-56d914107d64
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8aafb849a98028efb37646752a7b49fa5e6ef2ff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309560"
---
# <a name="iprofadmindeleteprofile"></a><span data-ttu-id="77f7b-103">IProfAdmin::DeleteProfile</span><span class="sxs-lookup"><span data-stu-id="77f7b-103">IProfAdmin::DeleteProfile</span></span>

  
  
<span data-ttu-id="77f7b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="77f7b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="77f7b-105">删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="77f7b-105">Deletes a profile.</span></span>
  
```cpp
HRESULT DeleteProfile(
  LPSTR lpszProfileName,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="77f7b-106">参数</span><span class="sxs-lookup"><span data-stu-id="77f7b-106">Parameters</span></span>

 <span data-ttu-id="77f7b-107">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="77f7b-107">_lpszProfileName_</span></span>
  
> <span data-ttu-id="77f7b-108">实时指向要删除的配置文件的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="77f7b-108">[in] A pointer to the name of the profile to be deleted.</span></span>
    
 <span data-ttu-id="77f7b-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="77f7b-109">_ulFlags_</span></span>
  
> <span data-ttu-id="77f7b-110">实时始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="77f7b-110">[in] Always NULL.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="77f7b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="77f7b-111">Return value</span></span>

<span data-ttu-id="77f7b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="77f7b-112">S_OK</span></span> 
  
> <span data-ttu-id="77f7b-113">已成功删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="77f7b-113">The profile was successfully deleted.</span></span>
    
<span data-ttu-id="77f7b-114">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="77f7b-114">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="77f7b-115">指定的配置文件不存在。</span><span class="sxs-lookup"><span data-stu-id="77f7b-115">The specified profile does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="77f7b-116">注解</span><span class="sxs-lookup"><span data-stu-id="77f7b-116">Remarks</span></span>

<span data-ttu-id="77f7b-117">**IProfAdmin::D eleteprofile**方法删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="77f7b-117">The **IProfAdmin::DeleteProfile** method deletes a profile.</span></span> <span data-ttu-id="77f7b-118">如果调用**DeleteProfile**时正在使用要删除的配置文件, 则**DeleteProfile**将返回 S_OK, 但不会立即删除该配置文件。</span><span class="sxs-lookup"><span data-stu-id="77f7b-118">If the profile to delete is in use when **DeleteProfile** is called, **DeleteProfile** returns S_OK but does not delete the profile immediately.</span></span> <span data-ttu-id="77f7b-119">相反, **DeleteProfile**将该配置文件标记为删除, 并在它不再使用后将其删除, 并在所有活动会话结束后将其删除。</span><span class="sxs-lookup"><span data-stu-id="77f7b-119">Instead, **DeleteProfile** marks the profile for deletion and deletes it after it is no longer being used, when all of its active sessions have ended.</span></span> 
  
<span data-ttu-id="77f7b-120">将使用_ulContext_参数中设置的 MSG_SERVICE_DELETE 值调用配置文件中每个邮件服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="77f7b-120">The entry point function for each message service in the profile is called with the MSG_SERVICE_DELETE value set in the  _ulContext_ parameter.</span></span> <span data-ttu-id="77f7b-121">首先, 函数删除该服务, 然后删除该服务的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="77f7b-121">First, the function deletes the service, and then it deletes the service's profile section.</span></span> <span data-ttu-id="77f7b-122">删除服务后, 不会再次调用邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="77f7b-122">The message service entry point function is not called again after the service has been deleted.</span></span> 
  
<span data-ttu-id="77f7b-123">删除配置文件不需要密码。</span><span class="sxs-lookup"><span data-stu-id="77f7b-123">No password is required to delete a profile.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="77f7b-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="77f7b-124">MFCMAPI reference</span></span>

<span data-ttu-id="77f7b-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="77f7b-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="77f7b-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="77f7b-126">**File**</span></span>|<span data-ttu-id="77f7b-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="77f7b-127">**Function**</span></span>|<span data-ttu-id="77f7b-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="77f7b-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77f7b-129">MAPIProfileFunctions</span><span class="sxs-lookup"><span data-stu-id="77f7b-129">MAPIProfileFunctions.cpp</span></span>  <br/> |<span data-ttu-id="77f7b-130">HrRemoveProfile</span><span class="sxs-lookup"><span data-stu-id="77f7b-130">HrRemoveProfile</span></span>  <br/> |<span data-ttu-id="77f7b-131">MFCMAPI 使用**IProfAdmin::D eleteprofile**方法删除选定的配置文件。</span><span class="sxs-lookup"><span data-stu-id="77f7b-131">MFCMAPI uses the **IProfAdmin::DeleteProfile** method to delete the selected profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="77f7b-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77f7b-132">See also</span></span>



[<span data-ttu-id="77f7b-133">IMsgServiceAdmin::DeleteMsgService</span><span class="sxs-lookup"><span data-stu-id="77f7b-133">IMsgServiceAdmin::DeleteMsgService</span></span>](imsgserviceadmin-deletemsgservice.md)
  
[<span data-ttu-id="77f7b-134">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="77f7b-134">MSGSERVICEENTRY</span></span>](msgserviceentry.md)
  
[<span data-ttu-id="77f7b-135">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="77f7b-135">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)


[<span data-ttu-id="77f7b-136">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="77f7b-136">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

