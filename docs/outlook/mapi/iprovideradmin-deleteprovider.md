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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 28dbbb98c9810bb688b9ecdd730ef6c4ada5f60b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279547"
---
# <a name="iprovideradmindeleteprovider"></a><span data-ttu-id="99209-103">IProviderAdmin::DeleteProvider</span><span class="sxs-lookup"><span data-stu-id="99209-103">IProviderAdmin::DeleteProvider</span></span>

  
  
<span data-ttu-id="99209-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="99209-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="99209-105">从邮件服务中删除服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="99209-105">Deletes a service provider from the message service.</span></span>
  
```cpp
HRESULT DeleteProvider(
  LPMAPIUID lpUID
);
```

## <a name="parameters"></a><span data-ttu-id="99209-106">参数</span><span class="sxs-lookup"><span data-stu-id="99209-106">Parameters</span></span>

 <span data-ttu-id="99209-107">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="99209-107">_lpUID_</span></span>
  
> <span data-ttu-id="99209-108">[in, out]指向[MAPIUID](mapiuid.md)结构的指针, 该对象包含表示要删除的提供程序的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="99209-108">[in, out] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier that represents the provider to delete.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="99209-109">返回值</span><span class="sxs-lookup"><span data-stu-id="99209-109">Return value</span></span>

<span data-ttu-id="99209-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="99209-110">S_OK</span></span> 
  
> <span data-ttu-id="99209-111">已成功从邮件服务中删除提供程序。</span><span class="sxs-lookup"><span data-stu-id="99209-111">The provider was successfully deleted from the message service.</span></span>
    
<span data-ttu-id="99209-112">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="99209-112">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="99209-113">无法识别_lpUID_参数指向的**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="99209-113">The **MAPIUID** pointed to by the  _lpUID_ parameter was not recognized.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="99209-114">注解</span><span class="sxs-lookup"><span data-stu-id="99209-114">Remarks</span></span>

<span data-ttu-id="99209-115">**IProviderAdmin::D eleteprovider**方法从邮件服务中删除服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="99209-115">The **IProviderAdmin::DeleteProvider** method deletes a service provider from the message service.</span></span> <span data-ttu-id="99209-116">**DeleteProvider**确定要删除的服务提供程序, 方法是将_lpUID_所指向的**MAPIUID**结构与活动服务提供商注册的一组标识符相匹配。</span><span class="sxs-lookup"><span data-stu-id="99209-116">**DeleteProvider** determines the service provider to delete by matching the **MAPIUID** structure pointed to by  _lpUID_ with the set of identifiers registered by the active service providers.</span></span> 
  
<span data-ttu-id="99209-117">大多数邮件服务不允许在配置文件正在使用时删除提供程序。</span><span class="sxs-lookup"><span data-stu-id="99209-117">Most message services do not allow providers to be deleted while the profile is in use.</span></span> <span data-ttu-id="99209-118">如果要删除的提供程序正在使用中, **DeleteProvider**会将其标记为删除, 而不是立即删除它并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="99209-118">If the provider to delete is in use, **DeleteProvider** marks it for deletion instead of removing it immediately and returns S_OK.</span></span> <span data-ttu-id="99209-119">如果不再使用该提供程序, 则将其删除。</span><span class="sxs-lookup"><span data-stu-id="99209-119">When the provider is no longer being used, it is deleted.</span></span> 
  
 <span data-ttu-id="99209-120">在从服务中删除提供程序之前, **DeleteProvider**调用邮件服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="99209-120">**DeleteProvider** calls the message service's entry point function before the provider is removed from the service.</span></span> <span data-ttu-id="99209-121">_ulContext_参数设置为 MSG_SERVICE_PROVIDER_DELETE。</span><span class="sxs-lookup"><span data-stu-id="99209-121">The  _ulContext_ parameter is set to MSG_SERVICE_PROVIDER_DELETE.</span></span> <span data-ttu-id="99209-122">邮件服务入口点函数执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="99209-122">The message service entry point function performs the following tasks:</span></span> 
  
- <span data-ttu-id="99209-123">删除服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="99209-123">Deletes the service provider.</span></span>
    
- <span data-ttu-id="99209-124">删除服务提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="99209-124">Deletes the service provider's profile section.</span></span>
    
<span data-ttu-id="99209-125">删除提供程序后, 不会再次调用邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="99209-125">The message service entry point function is not called again after the provider has been deleted.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99209-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99209-126">See also</span></span>



[<span data-ttu-id="99209-127">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="99209-127">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="99209-128">MSGSERVICEENTRY</span><span class="sxs-lookup"><span data-stu-id="99209-128">MSGSERVICEENTRY</span></span>](msgserviceentry.md)
  
[<span data-ttu-id="99209-129">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="99209-129">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)

