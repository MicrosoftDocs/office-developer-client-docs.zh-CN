---
title: HrCreateOfflineObj
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 04d57c1d-ce91-42ce-9f0f-00563092f6f4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f86266f192ffb1c86ca48f0fd5f99559737a9e76
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576482"
---
# <a name="hrcreateofflineobj"></a><span data-ttu-id="2cf9a-103">HrCreateOfflineObj</span><span class="sxs-lookup"><span data-stu-id="2cf9a-103">HrCreateOfflineObj</span></span>

<span data-ttu-id="2cf9a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2cf9a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="2cf9a-105">创建一个 MAPI 脱机对象，以便通知 MAPI，当对象联机和脱机，使用提供程序和存储</span><span class="sxs-lookup"><span data-stu-id="2cf9a-105">Creates a MAPI offline object that is used by the provider and store in order to notify MAPI when the object goes online and offline,</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2cf9a-106">导出：</span><span class="sxs-lookup"><span data-stu-id="2cf9a-106">Exported by:</span></span>  <br/> |<span data-ttu-id="2cf9a-107">Msmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="2cf9a-107">Msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="2cf9a-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2cf9a-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2cf9a-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="2cf9a-109">Outlook</span></span>  <br/> |
|<span data-ttu-id="2cf9a-110">调用：</span><span class="sxs-lookup"><span data-stu-id="2cf9a-110">Called by:</span></span>  <br/> |<span data-ttu-id="2cf9a-111">客户端</span><span class="sxs-lookup"><span data-stu-id="2cf9a-111">Client</span></span>  <br/> |
   
```cpp
STDAPI HrCreateOfflineObj(
ULONG ulFlags,
MAPIOFFLINE_CREATEINFO* pCreateInfo,
IMAPIOfflineMgr** ppOffline
);
```

## <a name="parameters"></a><span data-ttu-id="2cf9a-112">参数</span><span class="sxs-lookup"><span data-stu-id="2cf9a-112">Parameters</span></span>

<span data-ttu-id="2cf9a-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2cf9a-113">_ulFlags_</span></span>
  
> <span data-ttu-id="2cf9a-114">[in]它必须是 0。</span><span class="sxs-lookup"><span data-stu-id="2cf9a-114">[in] It must be 0.</span></span>
    
<span data-ttu-id="2cf9a-115">_pCreateInfo_</span><span class="sxs-lookup"><span data-stu-id="2cf9a-115">_pCreateInfo_</span></span>
  
> <span data-ttu-id="2cf9a-116">[in]一个指向**MAPIOFFLINE_CREATEINFO**结构，其中包含创建脱机对象所需的信息。</span><span class="sxs-lookup"><span data-stu-id="2cf9a-116">[in] A pointer to a **MAPIOFFLINE_CREATEINFO** structure that contains the information needed to create the offline object.</span></span> 
    
<span data-ttu-id="2cf9a-117">_ppOffline_</span><span class="sxs-lookup"><span data-stu-id="2cf9a-117">_ppOffline_</span></span>
  
> <span data-ttu-id="2cf9a-118">[输出]指向**IMAPIOfflineMgr**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2cf9a-118">[out] A pointer to the **IMAPIOfflineMgr** interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2cf9a-119">返回值</span><span class="sxs-lookup"><span data-stu-id="2cf9a-119">Return value</span></span>

<span data-ttu-id="2cf9a-120">无。</span><span class="sxs-lookup"><span data-stu-id="2cf9a-120">None.</span></span>
  
<span data-ttu-id="2cf9a-121">HrOpenOfflineObj</span><span class="sxs-lookup"><span data-stu-id="2cf9a-121">HrOpenOfflineObj</span></span>
  
## <a name="example"></a><span data-ttu-id="2cf9a-122">示例</span><span class="sxs-lookup"><span data-stu-id="2cf9a-122">Example</span></span>

```cpp
// create/get global offline object to use as parent.
 ZeroMemory(&OfflineCreateInfo, sizeof(OfflineCreateInfo));
  OfflineCreateInfo.ulSize = sizeof(OfflineCreateInfo);
  OfflineCreateInfo.ulCreateFlags = 0;
  OfflineCreateInfo.pwszProfileName = pszProfileName;
  OfflineCreateInfo.ulCapabilities = ulCapabilities;
  OfflineCreateInfo.pGUID = &GUID_GlobalState;
  OfflineCreateInfo.pInstance = NULL;
  OfflineCreateInfo.pParent = NULL;
  OfflineCreateInfo.pMAPISupport = NULL;
  OfflineCreateInfo.pAggregateInfo = NULL;
  OfflineCreateInfo.pConnectInfo = NULL;
// Create an offline object for the provider with global as parent.
  ZeroMemory(&OfflineCreateInfo, sizeof(OfflineCreateInfo));
  OfflineCreateInfo.ulSize = sizeof(OfflineCreateInfo);
  OfflineCreateInfo.ulCreateFlags = 0;
  OfflineCreateInfo.pwszProfileName = pszProfileName;
  OfflineCreateInfo.ulCapabilities = ulCapabilities;
  OfflineCreateInfo.pGUID = pGuid;
  OfflineCreateInfo.pInstance = pInstance;
  OfflineCreateInfo.pParent = pGlobalOfflineMgr;
  OfflineCreateInfo.pMAPISupport = NULL;
  OfflineCreateInfo.pAggregateInfo = NULL;
  OfflineCreateInfo.pConnectInfo = NULL;
  // create store offline object which aggregates with the store object and has provider offline object as parent.
  ZeroMemory(&OfflineCreateInfo, sizeof(OfflineCreateInfo));
  OfflineCreateInfo.ulSize = sizeof(OfflineCreateInfo);
  OfflineCreateInfo.ulCreateFlags = 0;
  OfflineCreateInfo.pwszProfileName = pszProfileName;
  OfflineCreateInfo.ulCapabilities = ulCapabilities;
  OfflineCreateInfo.pGUID = NULL;
  OfflineCreateInfo.pInstance = NULL;
  OfflineCreateInfo.pParent = m_pProviderOfflineMgr;
  OfflineCreateInfo.pMAPISupport = pMAPISup;
  OfflineCreateInfo.pAggregateInfo = &AggregateInfo;
  OfflineCreateInfo.pConnectInfo = NULL;
  ZeroMemory(&AggregateInfo, sizeof(AggregateInfo));
  AggregateInfo.ulSize = sizeof(AggregateInfo);
  AggregateInfo.pOuterObj = (IMsgStore *)this;
  AggregateInfo.pRefTrackRoot = NULL;

```

## <a name="see-also"></a><span data-ttu-id="2cf9a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cf9a-123">See also</span></span>

- [<span data-ttu-id="2cf9a-124">MAPIOFFLINE_AGGREGATEINFO</span><span class="sxs-lookup"><span data-stu-id="2cf9a-124">MAPIOFFLINE_AGGREGATEINFO</span></span>](mapioffline_aggregateinfo.md)
- [<span data-ttu-id="2cf9a-125">MAPIOFFLINE_CREATEINFO</span><span class="sxs-lookup"><span data-stu-id="2cf9a-125">MAPIOFFLINE_CREATEINFO</span></span>](mapioffline_createinfo.md)

