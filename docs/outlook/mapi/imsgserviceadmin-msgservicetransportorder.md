---
title: IMsgServiceAdminMsgServiceTransportOrder
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.MsgServiceTransportOrder
api_type:
- COM
ms.assetid: c57ada0e-b9a1-496b-8548-75686d8cba4e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 559f1c609000608d0eb920a0240ac8848e4bc2a7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570791"
---
# <a name="imsgserviceadminmsgservicetransportorder"></a><span data-ttu-id="8f210-103">IMsgServiceAdmin::MsgServiceTransportOrder</span><span class="sxs-lookup"><span data-stu-id="8f210-103">IMsgServiceAdmin::MsgServiceTransportOrder</span></span>

  
  
<span data-ttu-id="8f210-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8f210-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8f210-105">设置中的传输提供程序调用将邮件传递的顺序。</span><span class="sxs-lookup"><span data-stu-id="8f210-105">Sets the order in which transport providers are called to deliver a message.</span></span>
  
```cpp
HRESULT MsgServiceTransportOrder(
  ULONG cUID,
  LPMAPIUID lpUIDList,
  ULONG ulFlags    
);
```

## <a name="parameters"></a><span data-ttu-id="8f210-106">参数</span><span class="sxs-lookup"><span data-stu-id="8f210-106">Parameters</span></span>

 <span data-ttu-id="8f210-107">_cUID_</span><span class="sxs-lookup"><span data-stu-id="8f210-107">_cUID_</span></span>
  
> <span data-ttu-id="8f210-108">[in]_LpUIDList_参数中的唯一标识符的计数。</span><span class="sxs-lookup"><span data-stu-id="8f210-108">[in] The count of unique identifiers in the  _lpUIDList_ parameter.</span></span> 
    
 <span data-ttu-id="8f210-109">_lpUIDList_</span><span class="sxs-lookup"><span data-stu-id="8f210-109">_lpUIDList_</span></span>
  
> <span data-ttu-id="8f210-110">[in]一个指向代表传输提供程序的唯一标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="8f210-110">[in] A pointer to an array of unique identifiers that represent transport providers.</span></span> <span data-ttu-id="8f210-111">该数组中的当前配置文件配置每个传输提供程序包含一个标识符。</span><span class="sxs-lookup"><span data-stu-id="8f210-111">The array contains one identifier for each transport provider configured in the current profile.</span></span>
    
 <span data-ttu-id="8f210-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8f210-112">_ulFlags_</span></span>
  
> <span data-ttu-id="8f210-113">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="8f210-113">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8f210-114">返回值</span><span class="sxs-lookup"><span data-stu-id="8f210-114">Return value</span></span>

<span data-ttu-id="8f210-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f210-115">S_OK</span></span> 
  
> <span data-ttu-id="8f210-116">已成功设置传输顺序。</span><span class="sxs-lookup"><span data-stu-id="8f210-116">The transport order was set successfully.</span></span>
    
<span data-ttu-id="8f210-117">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="8f210-117">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="8f210-118">_CUID_参数中的值不同于实际配置文件中的传输提供程序的数目。</span><span class="sxs-lookup"><span data-stu-id="8f210-118">The value in the  _cUID_ parameter differs from the number of transport providers actually in the profile.</span></span> 
    
<span data-ttu-id="8f210-119">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="8f210-119">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="8f210-120">一个或多个_lpUIDList_参数中传递的[MAPIUID](mapiuid.md)结构不引用当前配置文件中的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="8f210-120">One or more of the [MAPIUID](mapiuid.md) structures passed in the  _lpUIDList_ parameter do not refer to a transport provider currently in the profile.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="8f210-121">注解</span><span class="sxs-lookup"><span data-stu-id="8f210-121">Remarks</span></span>

<span data-ttu-id="8f210-122">**IMsgServiceAdmin::MsgServiceTransportOrder**方法设置配置文件中的传输提供程序传递的顺序。</span><span class="sxs-lookup"><span data-stu-id="8f210-122">The **IMsgServiceAdmin::MsgServiceTransportOrder** method sets the delivery order of transport providers in a profile.</span></span> <span data-ttu-id="8f210-123">_LpUIDList_参数必须包含传输提供程序条目标识符从[IMsgServiceAdmin 从返回的表的**PR_PROVIDER_UID** ([PidTagProviderUid](pidtagprovideruid-canonical-property.md)) 属性获取一个已排序的列表：GetProviderTable](imsgserviceadmin-getprovidertable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8f210-123">The  _lpUIDList_ parameter must contain a sorted list of transport-provider entry identifiers obtained from the **PR_PROVIDER_UID** ([PidTagProviderUid](pidtagprovideruid-canonical-property.md)) property of the table returned from the [IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md) method.</span></span> <span data-ttu-id="8f210-124">客户端应用程序必须_lpUIDList_中传递的完整列表。</span><span class="sxs-lookup"><span data-stu-id="8f210-124">A client application must pass the complete list in  _lpUIDList_.</span></span>
  
 <span data-ttu-id="8f210-125">**SetTransportOrder**覆盖传输提供程序首选项，如**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置 STATUS_XP_PREFER_LAST 标志。</span><span class="sxs-lookup"><span data-stu-id="8f210-125">**SetTransportOrder** overrides transport provider preferences such as the STATUS_XP_PREFER_LAST flag set in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8f210-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f210-126">See also</span></span>



[<span data-ttu-id="8f210-127">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="8f210-127">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="8f210-128">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8f210-128">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

