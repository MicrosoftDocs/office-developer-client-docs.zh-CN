---
title: MAPIOFFLINE_ADVISEINFO
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 20a46c69-d6ae-7d17-f8af-12952867d342
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 443644b66ba9c961992e22dbfc260fe8c48fe1b3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776372"
---
# <a name="mapiofflineadviseinfo"></a><span data-ttu-id="cab50-103">MAPIOFFLINE_ADVISEINFO</span><span class="sxs-lookup"><span data-stu-id="cab50-103">MAPIOFFLINE_ADVISEINFO</span></span>
 
<span data-ttu-id="cab50-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cab50-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cab50-105">向**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 注册回调脱机对象提供信息。</span><span class="sxs-lookup"><span data-stu-id="cab50-105">Provides information to **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** to register callback for an offline object.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="cab50-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="cab50-106">Quick info</span></span>

<span data-ttu-id="cab50-107">请参阅**IMAPIOfflineMgr::Advise**。</span><span class="sxs-lookup"><span data-stu-id="cab50-107">See **IMAPIOfflineMgr::Advise**.</span></span> 
  
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

## <a name="members"></a><span data-ttu-id="cab50-108">Members</span><span class="sxs-lookup"><span data-stu-id="cab50-108">Members</span></span>

<span data-ttu-id="cab50-109">_ulSize_: **MAPIOFFLINE_ADVISEINFO**的大小。</span><span class="sxs-lookup"><span data-stu-id="cab50-109">_ulSize_: The size of **MAPIOFFLINE_ADVISEINFO**.</span></span> 
    
<span data-ttu-id="cab50-110">_ulClientToken_： 定义由客户端有关回调令牌。</span><span class="sxs-lookup"><span data-stu-id="cab50-110">_ulClientToken_: A token defined by the client about a callback.</span></span> <span data-ttu-id="cab50-111">它是传递给**[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)** **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)** 结构的*ulClientToken*成员。</span><span class="sxs-lookup"><span data-stu-id="cab50-111">It is the *ulClientToken* member of the **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)** structure passed to **[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)**.</span></span> 
    
<span data-ttu-id="cab50-112">_CallbackType_： 回调进行的类型。</span><span class="sxs-lookup"><span data-stu-id="cab50-112">_CallbackType_: Type of callback to make.</span></span>
    
   -  <span data-ttu-id="cab50-113">MAPIOFFLINE_CALLBACK_TYPE_NOTIFY</span><span class="sxs-lookup"><span data-stu-id="cab50-113">MAPIOFFLINE_CALLBACK_TYPE_NOTIFY</span></span> 
    
   - <span data-ttu-id="cab50-114">回调的类型是由通知。</span><span class="sxs-lookup"><span data-stu-id="cab50-114">The type of callback is by notification.</span></span> <span data-ttu-id="cab50-115">这是回调的唯一受支持类型。</span><span class="sxs-lookup"><span data-stu-id="cab50-115">This is the only supported type of callback.</span></span>  <span data-ttu-id="cab50-116">*pCallback*必须指明**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 的接口。</span><span class="sxs-lookup"><span data-stu-id="cab50-116">*pCallback*  must indicate the interface **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
    
<span data-ttu-id="cab50-117">_pCallback_： 接口用于回调。</span><span class="sxs-lookup"><span data-stu-id="cab50-117">_pCallback_: Interface to use for callback.</span></span> <span data-ttu-id="cab50-118">这是**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 的客户端的实现。</span><span class="sxs-lookup"><span data-stu-id="cab50-118">This is the client's implementation of **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
    
<span data-ttu-id="cab50-119">_ulAdviseTypes_: advise，如标识的条件的建议的类型。</span><span class="sxs-lookup"><span data-stu-id="cab50-119">_ulAdviseTypes_: The types of advise, as identified by the condition for advising.</span></span> <span data-ttu-id="cab50-120">MAPIOFFLINE_ADVISE_TYPE_STATECHANGE 唯一支持的类型。</span><span class="sxs-lookup"><span data-stu-id="cab50-120">The only supported type is MAPIOFFLINE_ADVISE_TYPE_STATECHANGE.</span></span>
    
<span data-ttu-id="cab50-121">_ulStateMask_： 只有受支持的状态是 MAPIOFFLINE_STATE_ALL。</span><span class="sxs-lookup"><span data-stu-id="cab50-121">_ulStateMask_: The only supported state is MAPIOFFLINE_STATE_ALL.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cab50-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cab50-122">See also</span></span>

- [<span data-ttu-id="cab50-123">IMAPIOfflineMgr::Advise</span><span class="sxs-lookup"><span data-stu-id="cab50-123">IMAPIOfflineMgr::Advise</span></span>](imapiofflinemgr-advise.md)
- [<span data-ttu-id="cab50-124">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="cab50-124">About the Offline State API</span></span>](about-the-offline-state-api.md) 
- [<span data-ttu-id="cab50-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="cab50-125">MAPI Constants</span></span>](mapi-constants.md) 
- [<span data-ttu-id="cab50-126">MAPIOFFLINE_CALLBACK_TYPE</span><span class="sxs-lookup"><span data-stu-id="cab50-126">MAPIOFFLINE_CALLBACK_TYPE</span></span>](mapioffline_callback_type.md)

