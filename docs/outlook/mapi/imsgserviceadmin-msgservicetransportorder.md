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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3d532e0eb46daa412711344421936a58da309b7b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420092"
---
# <a name="imsgserviceadminmsgservicetransportorder"></a><span data-ttu-id="fdb33-103">IMsgServiceAdmin::MsgServiceTransportOrder</span><span class="sxs-lookup"><span data-stu-id="fdb33-103">IMsgServiceAdmin::MsgServiceTransportOrder</span></span>

  
  
<span data-ttu-id="fdb33-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fdb33-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fdb33-105">设置调用传输提供程序以传递邮件的顺序。</span><span class="sxs-lookup"><span data-stu-id="fdb33-105">Sets the order in which transport providers are called to deliver a message.</span></span>
  
```cpp
HRESULT MsgServiceTransportOrder(
  ULONG cUID,
  LPMAPIUID lpUIDList,
  ULONG ulFlags    
);
```

## <a name="parameters"></a><span data-ttu-id="fdb33-106">参数</span><span class="sxs-lookup"><span data-stu-id="fdb33-106">Parameters</span></span>

 <span data-ttu-id="fdb33-107">_cUID_</span><span class="sxs-lookup"><span data-stu-id="fdb33-107">_cUID_</span></span>
  
> <span data-ttu-id="fdb33-108">[in]  _lpUIDList_ 参数中的唯一标识符计数。</span><span class="sxs-lookup"><span data-stu-id="fdb33-108">[in] The count of unique identifiers in the  _lpUIDList_ parameter.</span></span> 
    
 <span data-ttu-id="fdb33-109">_lpUIDList_</span><span class="sxs-lookup"><span data-stu-id="fdb33-109">_lpUIDList_</span></span>
  
> <span data-ttu-id="fdb33-110">[in]指向表示传输提供程序的唯一标识符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="fdb33-110">[in] A pointer to an array of unique identifiers that represent transport providers.</span></span> <span data-ttu-id="fdb33-111">数组包含当前配置文件中配置的每个传输提供程序的一个标识符。</span><span class="sxs-lookup"><span data-stu-id="fdb33-111">The array contains one identifier for each transport provider configured in the current profile.</span></span>
    
 <span data-ttu-id="fdb33-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fdb33-112">_ulFlags_</span></span>
  
> <span data-ttu-id="fdb33-113">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="fdb33-113">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fdb33-114">返回值</span><span class="sxs-lookup"><span data-stu-id="fdb33-114">Return value</span></span>

<span data-ttu-id="fdb33-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="fdb33-115">S_OK</span></span> 
  
> <span data-ttu-id="fdb33-116">已成功设置传输顺序。</span><span class="sxs-lookup"><span data-stu-id="fdb33-116">The transport order was set successfully.</span></span>
    
<span data-ttu-id="fdb33-117">MAPI_E_BUSY</span><span class="sxs-lookup"><span data-stu-id="fdb33-117">MAPI_E_BUSY</span></span> 
  
> <span data-ttu-id="fdb33-118">_cUID_ 参数中的值与配置文件中实际传输提供程序的数量不同。</span><span class="sxs-lookup"><span data-stu-id="fdb33-118">The value in the  _cUID_ parameter differs from the number of transport providers actually in the profile.</span></span> 
    
<span data-ttu-id="fdb33-119">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="fdb33-119">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="fdb33-120">在 _lpUIDList_ 参数中传递的一个或多个 [MAPIUID](mapiuid.md)结构不引用配置文件中的当前传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="fdb33-120">One or more of the [MAPIUID](mapiuid.md) structures passed in the  _lpUIDList_ parameter do not refer to a transport provider currently in the profile.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="fdb33-121">备注</span><span class="sxs-lookup"><span data-stu-id="fdb33-121">Remarks</span></span>

<span data-ttu-id="fdb33-122">**IMsgServiceAdmin：：MsgServiceTransportOrder** 方法设置配置文件中传输提供程序的传递顺序。</span><span class="sxs-lookup"><span data-stu-id="fdb33-122">The **IMsgServiceAdmin::MsgServiceTransportOrder** method sets the delivery order of transport providers in a profile.</span></span> <span data-ttu-id="fdb33-123">_lpUIDList_ 参数必须包含从从 [IMsgServiceAdmin：：GetProviderTable](imsgserviceadmin-getprovidertable.md)方法返回的表的 **PR_PROVIDER_UID** ([PidTagProviderUid](pidtagprovideruid-canonical-property.md)) 属性获取的传输提供程序条目标识符的排序列表。</span><span class="sxs-lookup"><span data-stu-id="fdb33-123">The  _lpUIDList_ parameter must contain a sorted list of transport-provider entry identifiers obtained from the **PR_PROVIDER_UID** ([PidTagProviderUid](pidtagprovideruid-canonical-property.md)) property of the table returned from the [IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md) method.</span></span> <span data-ttu-id="fdb33-124">客户端应用程序必须在  _lpUIDList 中传递完整列表_。</span><span class="sxs-lookup"><span data-stu-id="fdb33-124">A client application must pass the complete list in  _lpUIDList_.</span></span>
  
 <span data-ttu-id="fdb33-125">**SetTransportOrder** 重写传输提供程序首选项，如 PR_RESOURCE_FLAGS ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 设置 STATUS_XP_PREFER_LAST 标志。 </span><span class="sxs-lookup"><span data-stu-id="fdb33-125">**SetTransportOrder** overrides transport provider preferences such as the STATUS_XP_PREFER_LAST flag set in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fdb33-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdb33-126">See also</span></span>



[<span data-ttu-id="fdb33-127">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="fdb33-127">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="fdb33-128">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fdb33-128">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

