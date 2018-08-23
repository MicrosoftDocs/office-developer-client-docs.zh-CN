---
title: IMsgServiceAdminAdminProviders
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.AdminProviders
api_type:
- COM
ms.assetid: 0d605e2c-10db-46e1-95d5-12fabd524baa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1b03245d7af4c6fb3879e597d8345e5d9888e164
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567207"
---
# <a name="imsgserviceadminadminproviders"></a><span data-ttu-id="d1cd8-103">IMsgServiceAdmin::AdminProviders</span><span class="sxs-lookup"><span data-stu-id="d1cd8-103">IMsgServiceAdmin::AdminProviders</span></span>

  
  
<span data-ttu-id="d1cd8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1cd8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1cd8-105">返回提供访问提供程序管理对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-105">Returns a pointer that provides access to a provider administration object.</span></span>
  
```cpp
HRESULT AdminProviders(
  LPMAPIUID lpUID,
  ULONG ulFlags,
  LPPROVIDERADMIN FAR * lppProviderAdmin
);
```

## <a name="parameters"></a><span data-ttu-id="d1cd8-106">参数</span><span class="sxs-lookup"><span data-stu-id="d1cd8-106">Parameters</span></span>

 <span data-ttu-id="d1cd8-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="d1cd8-107">_lpUID_</span></span>
  
> <span data-ttu-id="d1cd8-108">[in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要从中要管理的消息服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-108">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the message service to be administered.</span></span> 
    
 <span data-ttu-id="d1cd8-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d1cd8-109">_ulFlags_</span></span>
  
> <span data-ttu-id="d1cd8-110">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-110">[in] Always NULL.</span></span> 
    
 <span data-ttu-id="d1cd8-111">_lppProviderAdmin_</span><span class="sxs-lookup"><span data-stu-id="d1cd8-111">_lppProviderAdmin_</span></span>
  
> <span data-ttu-id="d1cd8-112">[输出]指向提供程序的管理对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-112">[out] A pointer to a pointer to a provider administration object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d1cd8-113">返回值</span><span class="sxs-lookup"><span data-stu-id="d1cd8-113">Return value</span></span>

<span data-ttu-id="d1cd8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d1cd8-114">S_OK</span></span> 
  
> <span data-ttu-id="d1cd8-115">已成功返回的提供程序的管理对象。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-115">The provider administration object was successfully returned.</span></span>
    
<span data-ttu-id="d1cd8-116">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="d1cd8-116">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="d1cd8-117">**MAPIUID**由_lpUID_指向不存在。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-117">The **MAPIUID** pointed to by  _lpUID_ does not exist.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d1cd8-118">注解</span><span class="sxs-lookup"><span data-stu-id="d1cd8-118">Remarks</span></span>

<span data-ttu-id="d1cd8-119">**IMsgServiceAdmin::AdminProviders**方法提供对提供程序的管理对象访问。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-119">The **IMsgServiceAdmin::AdminProviders** method provides access to a provider administration object.</span></span> <span data-ttu-id="d1cd8-120">提供程序管理是对象支持[IProviderAdmin](iprovideradminiunknown.md)接口，使客户端执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d1cd8-120">A provider administration is an object that supports the [IProviderAdmin](iprovideradminiunknown.md) interface and enables clients to do the following:</span></span> 
  
- <span data-ttu-id="d1cd8-121">添加到消息服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-121">Add service providers to a message service.</span></span>
    
- <span data-ttu-id="d1cd8-122">删除消息服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-122">Delete service providers from a message service.</span></span>
    
- <span data-ttu-id="d1cd8-123">打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-123">Open profile sections.</span></span>
    
- <span data-ttu-id="d1cd8-124">访问邮件服务提供程序表。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-124">Access the message service provider table.</span></span>
    
<span data-ttu-id="d1cd8-125">在使用配置文件时可以实际的消息服务对做的更改的类型取决于邮件服务。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-125">The types of changes that can actually be made to a message service while the profile is in use depend on the message service.</span></span> <span data-ttu-id="d1cd8-126">但是，大多数消息服务不支持更改如添加和删除提供程序配置文件时使用。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-126">However, most message services do not support changes such as adding and deleting providers while the profile is in use.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="d1cd8-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d1cd8-127">Notes to callers</span></span>

<span data-ttu-id="d1cd8-128">若要检索要管理的消息服务的**MAPIUID**结构，请从邮件服务表中的消息服务的行中检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性列。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-128">To retrieve the **MAPIUID** structure for the message service to administer, retrieve the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property column from the message service's row in the message service table.</span></span> <span data-ttu-id="d1cd8-129">有关详细信息，请参阅[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)方法中概述的过程。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-129">For more information, see the procedure outlined in the [IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="d1cd8-130">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="d1cd8-130">MFCMAPI reference</span></span>

<span data-ttu-id="d1cd8-131">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="d1cd8-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="d1cd8-132">**File**</span></span>|<span data-ttu-id="d1cd8-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="d1cd8-133">**Function**</span></span>|<span data-ttu-id="d1cd8-134">**Comment**</span><span class="sxs-lookup"><span data-stu-id="d1cd8-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d1cd8-135">MsgServiceTableDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="d1cd8-135">MsgServiceTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="d1cd8-136">CMsgServiceTableDlg::OnDisplayItem</span><span class="sxs-lookup"><span data-stu-id="d1cd8-136">CMsgServiceTableDlg::OnDisplayItem</span></span>  <br/> |<span data-ttu-id="d1cd8-137">MFCMAPI 使用**IMsgServiceAdmin::AdminProviders**方法打开服务提供程序管理对象。</span><span class="sxs-lookup"><span data-stu-id="d1cd8-137">MFCMAPI uses the **IMsgServiceAdmin::AdminProviders** method to open a provider administration object for a service.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d1cd8-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1cd8-138">See also</span></span>



[<span data-ttu-id="d1cd8-139">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d1cd8-139">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)
  
[<span data-ttu-id="d1cd8-140">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="d1cd8-140">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="d1cd8-141">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d1cd8-141">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="d1cd8-142">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="d1cd8-142">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

