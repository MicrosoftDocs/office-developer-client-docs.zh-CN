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
ms.openlocfilehash: 5b96a45bab4cd00d23604d0b0b25f3e772277395
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775864"
---
# <a name="imsgserviceadminmsgservicetransportorder"></a><span data-ttu-id="d923a-103">IMsgServiceAdmin::MsgServiceTransportOrder</span><span class="sxs-lookup"><span data-stu-id="d923a-103">IMsgServiceAdmin::MsgServiceTransportOrder</span></span>

  
  
<span data-ttu-id="d923a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d923a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d923a-105">设置中的传输提供程序调用将邮件传递的顺序。</span><span class="sxs-lookup"><span data-stu-id="d923a-105">Sets the order in which transport providers are called to deliver a message.</span></span>
  
```cpp
HRESULT MsgServiceTransportOrder(
  ULONG cUID,
  LPMAPIUID lpUIDList,
  ULONG ulFlags    
);
```

## <a name="parameters"></a><span data-ttu-id="d923a-106">参数</span><span class="sxs-lookup"><span data-stu-id="d923a-106">Parameters</span></span>

 <span data-ttu-id="d923a-107">_cUID_</span><span class="sxs-lookup"><span data-stu-id="d923a-107">_cUID_</span></span>
  
> <span data-ttu-id="d923a-108">[in]_LpUIDList_参数中的唯一标识符的计数。</span><span class="sxs-lookup"><span data-stu-id="d923a-108">[in] The count of unique identifiers in the  _lpUIDList_ parameter.</span></span> 
    
 <span data-ttu-id="d923a-109">_lpUIDList_</span><span class="sxs-lookup"><span data-stu-id="d923a-109">_lpUIDList_</span></span>
  
> <span data-ttu-id="d923a-110">[in]一个指向代表传输提供程序的唯一标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="d923a-110">[in] A pointer to an array of unique identifiers that represent transport providers.</span></span> <span data-ttu-id="d923a-111">该数组中的当前配置文件配置每个传输提供程序包含一个标识符。</span><span class="sxs-lookup"><span data-stu-id="d923a-111">The array contains one identifier for each transport provider configured in the current profile.</span></span>
    
 <span data-ttu-id="d923a-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d923a-112">_ulFlags_</span></span>
  
> <span data-ttu-id="d923a-113">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="d923a-113">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d923a-114">返回值</span><span class="sxs-lookup"><span data-stu-id="d923a-114">Return value</span></span>

<span data-ttu-id="d923a-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d923a-115">S_OK</span></span> 
  
> <span data-ttu-id="d923a-116">已成功设置传输顺序。</span><span class="sxs-lookup"><span data-stu-id="d923a-116">The transport order was set successfully.</span></span>
    
<span data-ttu-id="d923a-117">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="d923a-117">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="d923a-118">_CUID_参数中的值不同于实际配置文件中的传输提供程序的数目。</span><span class="sxs-lookup"><span data-stu-id="d923a-118">The value in the  _cUID_ parameter differs from the number of transport providers actually in the profile.</span></span> 
    
<span data-ttu-id="d923a-119">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="d923a-119">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="d923a-120">一个或多个_lpUIDList_参数中传递的[MAPIUID](mapiuid.md)结构不引用当前配置文件中的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="d923a-120">One or more of the [MAPIUID](mapiuid.md) structures passed in the  _lpUIDList_ parameter do not refer to a transport provider currently in the profile.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d923a-121">备注</span><span class="sxs-lookup"><span data-stu-id="d923a-121">Remarks</span></span>

<span data-ttu-id="d923a-122">**IMsgServiceAdmin::MsgServiceTransportOrder**方法设置配置文件中的传输提供程序传递的顺序。</span><span class="sxs-lookup"><span data-stu-id="d923a-122">The **IMsgServiceAdmin::MsgServiceTransportOrder** method sets the delivery order of transport providers in a profile.</span></span> <span data-ttu-id="d923a-123">_LpUIDList_参数必须包含传输提供程序条目标识符从[IMsgServiceAdmin 从返回的表的**PR_PROVIDER_UID** ([PidTagProviderUid](pidtagprovideruid-canonical-property.md)) 属性获取一个已排序的列表：GetProviderTable](imsgserviceadmin-getprovidertable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d923a-123">The  _lpUIDList_ parameter must contain a sorted list of transport-provider entry identifiers obtained from the **PR_PROVIDER_UID** ([PidTagProviderUid](pidtagprovideruid-canonical-property.md)) property of the table returned from the [IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md) method.</span></span> <span data-ttu-id="d923a-124">客户端应用程序必须_lpUIDList_中传递的完整列表。</span><span class="sxs-lookup"><span data-stu-id="d923a-124">A client application must pass the complete list in  _lpUIDList_.</span></span>
  
 <span data-ttu-id="d923a-125">**SetTransportOrder**覆盖传输提供程序首选项，如**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置 STATUS_XP_PREFER_LAST 标志。</span><span class="sxs-lookup"><span data-stu-id="d923a-125">**SetTransportOrder** overrides transport provider preferences such as the STATUS_XP_PREFER_LAST flag set in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d923a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d923a-126">See also</span></span>



[<span data-ttu-id="d923a-127">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="d923a-127">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="d923a-128">IMsgServiceAdmin: IUnknown</span><span class="sxs-lookup"><span data-stu-id="d923a-128">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

