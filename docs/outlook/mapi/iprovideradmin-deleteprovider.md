---
title: IProviderAdminDeleteProvider
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin.DeleteProvider
api_type:
- COM
ms.assetid: 0065b50f-95f6-4af1-81c2-a73e5111eecf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e0f8dc1beeb669532e3731b38a4f03966403f76c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776011"
---
# <a name="iprovideradmindeleteprovider"></a><span data-ttu-id="14090-103">IProviderAdmin::DeleteProvider</span><span class="sxs-lookup"><span data-stu-id="14090-103">IProviderAdmin::DeleteProvider</span></span>

  
  
<span data-ttu-id="14090-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="14090-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="14090-105">删除消息服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="14090-105">Deletes a service provider from the message service.</span></span>
  
```cpp
HRESULT DeleteProvider(
  LPMAPIUID lpUID
);
```

## <a name="parameters"></a><span data-ttu-id="14090-106">参数</span><span class="sxs-lookup"><span data-stu-id="14090-106">Parameters</span></span>

 <span data-ttu-id="14090-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="14090-107">_lpUID_</span></span>
  
> <span data-ttu-id="14090-108">[传入、 传出]一个指向[MAPIUID](mapiuid.md)结构，其中包含代表要删除的提供程序的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="14090-108">[in, out] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier that represents the provider to delete.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="14090-109">返回值</span><span class="sxs-lookup"><span data-stu-id="14090-109">Return value</span></span>

<span data-ttu-id="14090-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="14090-110">S_OK</span></span> 
  
> <span data-ttu-id="14090-111">提供程序已成功删除从邮件服务。</span><span class="sxs-lookup"><span data-stu-id="14090-111">The provider was successfully deleted from the message service.</span></span>
    
<span data-ttu-id="14090-112">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="14090-112">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="14090-113">无法识别**MAPIUID** _lpUID_参数指向。</span><span class="sxs-lookup"><span data-stu-id="14090-113">The **MAPIUID** pointed to by the  _lpUID_ parameter was not recognized.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="14090-114">说明</span><span class="sxs-lookup"><span data-stu-id="14090-114">Remarks</span></span>

<span data-ttu-id="14090-115">**IProviderAdmin::DeleteProvider**方法删除消息服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="14090-115">The **IProviderAdmin::DeleteProvider** method deletes a service provider from the message service.</span></span> <span data-ttu-id="14090-116">**DeleteProvider**确定服务提供商删除匹配**MAPIUID**结构所指的_lpUID_注册的活动服务提供商的标识符的设置。</span><span class="sxs-lookup"><span data-stu-id="14090-116">**DeleteProvider** determines the service provider to delete by matching the **MAPIUID** structure pointed to by  _lpUID_ with the set of identifiers registered by the active service providers.</span></span> 
  
<span data-ttu-id="14090-117">大多数消息服务不允许使用配置文件时要删除的提供程序。</span><span class="sxs-lookup"><span data-stu-id="14090-117">Most message services do not allow providers to be deleted while the profile is in use.</span></span> <span data-ttu-id="14090-118">如果要删除的提供程序正在使用中， **DeleteProvider**将其标记为删除而不是立即删除并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="14090-118">If the provider to delete is in use, **DeleteProvider** marks it for deletion instead of removing it immediately and returns S_OK.</span></span> <span data-ttu-id="14090-119">不再使用提供程序时，则将其删除。</span><span class="sxs-lookup"><span data-stu-id="14090-119">When the provider is no longer being used, it is deleted.</span></span> 
  
 <span data-ttu-id="14090-120">从服务中删除提供程序之前， **DeleteProvider**调用消息服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="14090-120">**DeleteProvider** calls the message service's entry point function before the provider is removed from the service.</span></span> <span data-ttu-id="14090-121">_UlContext_参数设置为 MSG_SERVICE_PROVIDER_DELETE。</span><span class="sxs-lookup"><span data-stu-id="14090-121">The  _ulContext_ parameter is set to MSG_SERVICE_PROVIDER_DELETE.</span></span> <span data-ttu-id="14090-122">消息服务入口点函数执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="14090-122">The message service entry point function performs the following tasks:</span></span> 
  
- <span data-ttu-id="14090-123">删除服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="14090-123">Deletes the service provider.</span></span>
    
- <span data-ttu-id="14090-124">删除服务提供商的配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="14090-124">Deletes the service provider's profile section.</span></span>
    
<span data-ttu-id="14090-125">删除提供程序后，不是再次调用消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="14090-125">The message service entry point function is not called again after the provider has been deleted.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="14090-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14090-126">See also</span></span>



[<span data-ttu-id="14090-127">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="14090-127">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="14090-128">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="14090-128">MSGSERVICEENTRY</span></span>](msgserviceentry.md)
  
[<span data-ttu-id="14090-129">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="14090-129">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)

