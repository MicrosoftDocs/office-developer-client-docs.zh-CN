---
title: MAPIOFFLINE_ADVISEINFO
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 20a46c69-d6ae-7d17-f8af-12952867d342
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3cb110fdcbbd88e494c44ba2ed73cc26674638ca
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270033"
---
# <a name="mapiofflineadviseinfo"></a><span data-ttu-id="565fe-103">MAPIOFFLINE_ADVISEINFO</span><span class="sxs-lookup"><span data-stu-id="565fe-103">MAPIOFFLINE_ADVISEINFO</span></span>
 
<span data-ttu-id="565fe-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="565fe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="565fe-105">向**[IMAPIOfflineMgr:: 建议](imapiofflinemgr-advise.md)** 为脱机对象注册回调的信息。</span><span class="sxs-lookup"><span data-stu-id="565fe-105">Provides information to **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** to register callback for an offline object.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="565fe-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="565fe-106">Quick info</span></span>

<span data-ttu-id="565fe-107">请参阅**IMAPIOfflineMgr:: Advise**。</span><span class="sxs-lookup"><span data-stu-id="565fe-107">See **IMAPIOfflineMgr::Advise**.</span></span> 
  
```cpp
typedef struct 
{ 
      ULONG                   ulSize; 
      ULONG                   ulClientToken; 
      MAPIOFFLINE_CALLBACK_TYPE     CallbackType; 
      IUnknown*               pCallback; 
      ULONG                   ulAdviseTypes; 
      ULONG                   ulStateMask; 
} MAPIOFFLINE_ADVISEINFO;
```

## <a name="members"></a><span data-ttu-id="565fe-108">Members</span><span class="sxs-lookup"><span data-stu-id="565fe-108">Members</span></span>

<span data-ttu-id="565fe-109">_ulSize_: **MAPIOFFLINE_ADVISEINFO**的大小。</span><span class="sxs-lookup"><span data-stu-id="565fe-109">_ulSize_: The size of **MAPIOFFLINE_ADVISEINFO**.</span></span> 
    
<span data-ttu-id="565fe-110">_ulClientToken_: 客户端定义的有关回调的令牌。</span><span class="sxs-lookup"><span data-stu-id="565fe-110">_ulClientToken_: A token defined by the client about a callback.</span></span> <span data-ttu-id="565fe-111">它是传递给**[IMAPIOfflineNotify:: NOTIFY](imapiofflinenotify-notify.md)** 的**[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)** 结构的*ulClientToken*成员。</span><span class="sxs-lookup"><span data-stu-id="565fe-111">It is the *ulClientToken* member of the **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)** structure passed to **[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)**.</span></span> 
    
<span data-ttu-id="565fe-112">_CallbackType_: 要进行的回调类型。</span><span class="sxs-lookup"><span data-stu-id="565fe-112">_CallbackType_: Type of callback to make.</span></span>
    
   -  <span data-ttu-id="565fe-113">MAPIOFFLINE_CALLBACK_TYPE_NOTIFY</span><span class="sxs-lookup"><span data-stu-id="565fe-113">MAPIOFFLINE_CALLBACK_TYPE_NOTIFY</span></span> 
    
   - <span data-ttu-id="565fe-114">回调的类型为 "通知"。</span><span class="sxs-lookup"><span data-stu-id="565fe-114">The type of callback is by notification.</span></span> <span data-ttu-id="565fe-115">这是唯一受支持的回调类型。</span><span class="sxs-lookup"><span data-stu-id="565fe-115">This is the only supported type of callback.</span></span>  <span data-ttu-id="565fe-116">*pCallback*必须指示接口**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。</span><span class="sxs-lookup"><span data-stu-id="565fe-116">*pCallback*  must indicate the interface **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
    
<span data-ttu-id="565fe-117">_pCallback_: 用于回呼的接口。</span><span class="sxs-lookup"><span data-stu-id="565fe-117">_pCallback_: Interface to use for callback.</span></span> <span data-ttu-id="565fe-118">这是客户端的**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 实现。</span><span class="sxs-lookup"><span data-stu-id="565fe-118">This is the client's implementation of **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
    
<span data-ttu-id="565fe-119">_ulAdviseTypes_: 建议的类型, 由建议的条件标识。</span><span class="sxs-lookup"><span data-stu-id="565fe-119">_ulAdviseTypes_: The types of advise, as identified by the condition for advising.</span></span> <span data-ttu-id="565fe-120">唯一受支持的类型为 MAPIOFFLINE_ADVISE_TYPE_STATECHANGE。</span><span class="sxs-lookup"><span data-stu-id="565fe-120">The only supported type is MAPIOFFLINE_ADVISE_TYPE_STATECHANGE.</span></span>
    
<span data-ttu-id="565fe-121">_ulStateMask_: 唯一受支持的状态是 MAPIOFFLINE_STATE_ALL。</span><span class="sxs-lookup"><span data-stu-id="565fe-121">_ulStateMask_: The only supported state is MAPIOFFLINE_STATE_ALL.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="565fe-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="565fe-122">See also</span></span>

- [<span data-ttu-id="565fe-123">IMAPIOfflineMgr::Advise</span><span class="sxs-lookup"><span data-stu-id="565fe-123">IMAPIOfflineMgr::Advise</span></span>](imapiofflinemgr-advise.md)
- [<span data-ttu-id="565fe-124">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="565fe-124">About the Offline State API</span></span>](about-the-offline-state-api.md) 
- [<span data-ttu-id="565fe-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="565fe-125">MAPI Constants</span></span>](mapi-constants.md) 
- [<span data-ttu-id="565fe-126">MAPIOFFLINE_CALLBACK_TYPE</span><span class="sxs-lookup"><span data-stu-id="565fe-126">MAPIOFFLINE_CALLBACK_TYPE</span></span>](mapioffline_callback_type.md)

