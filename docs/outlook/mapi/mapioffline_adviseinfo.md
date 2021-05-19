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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420022"
---
# <a name="mapioffline_adviseinfo"></a><span data-ttu-id="290dc-103">MAPIOFFLINE_ADVISEINFO</span><span class="sxs-lookup"><span data-stu-id="290dc-103">MAPIOFFLINE_ADVISEINFO</span></span>
 
<span data-ttu-id="290dc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="290dc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="290dc-105">向 **[IMAPIOfflineMgr：：Advise](imapiofflinemgr-advise.md)** 提供为脱机对象注册回调的信息。</span><span class="sxs-lookup"><span data-stu-id="290dc-105">Provides information to **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** to register callback for an offline object.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="290dc-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="290dc-106">Quick info</span></span>

<span data-ttu-id="290dc-107">请参阅 **IMAPIOfflineMgr：：Advise**。</span><span class="sxs-lookup"><span data-stu-id="290dc-107">See **IMAPIOfflineMgr::Advise**.</span></span> 
  
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

## <a name="members"></a><span data-ttu-id="290dc-108">Members</span><span class="sxs-lookup"><span data-stu-id="290dc-108">Members</span></span>

<span data-ttu-id="290dc-109">_ulSize：MAPIOFFLINE_ADVISEINFO。_ </span><span class="sxs-lookup"><span data-stu-id="290dc-109">_ulSize_: The size of **MAPIOFFLINE_ADVISEINFO**.</span></span> 
    
<span data-ttu-id="290dc-110">_ulClientToken：_ 客户端定义的有关回调的令牌。</span><span class="sxs-lookup"><span data-stu-id="290dc-110">_ulClientToken_: A token defined by the client about a callback.</span></span> <span data-ttu-id="290dc-111">它是传递到 **[IMAPIOfflineNotify：：Notify](imapiofflinenotify-notify.md)\*\*\*\*[的](mapioffline_notify.md)** MAPIOFFLINE_NOTIFY 结构的 *ulClientToken* 成员。</span><span class="sxs-lookup"><span data-stu-id="290dc-111">It is the *ulClientToken* member of the **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)** structure passed to **[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)**.</span></span> 
    
<span data-ttu-id="290dc-112">_CallbackType：_ 要进行回调的类型。</span><span class="sxs-lookup"><span data-stu-id="290dc-112">_CallbackType_: Type of callback to make.</span></span>
    
   -  <span data-ttu-id="290dc-113">MAPIOFFLINE_CALLBACK_TYPE_NOTIFY</span><span class="sxs-lookup"><span data-stu-id="290dc-113">MAPIOFFLINE_CALLBACK_TYPE_NOTIFY</span></span> 
    
   - <span data-ttu-id="290dc-114">回调的类型是通知。</span><span class="sxs-lookup"><span data-stu-id="290dc-114">The type of callback is by notification.</span></span> <span data-ttu-id="290dc-115">这是唯一受支持的回调类型。</span><span class="sxs-lookup"><span data-stu-id="290dc-115">This is the only supported type of callback.</span></span>  <span data-ttu-id="290dc-116">*pCallback*  必须指示 **[接口 IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。</span><span class="sxs-lookup"><span data-stu-id="290dc-116">*pCallback*  must indicate the interface **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
    
<span data-ttu-id="290dc-117">_pCallback：_ 用于回调的接口。</span><span class="sxs-lookup"><span data-stu-id="290dc-117">_pCallback_: Interface to use for callback.</span></span> <span data-ttu-id="290dc-118">这是客户端对 **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 的实现。</span><span class="sxs-lookup"><span data-stu-id="290dc-118">This is the client's implementation of **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
    
<span data-ttu-id="290dc-119">_ulAdviseTypes：_ 建议类型，由建议条件标识。</span><span class="sxs-lookup"><span data-stu-id="290dc-119">_ulAdviseTypes_: The types of advise, as identified by the condition for advising.</span></span> <span data-ttu-id="290dc-120">唯一受支持的类型是 MAPIOFFLINE_ADVISE_TYPE_STATECHANGE。</span><span class="sxs-lookup"><span data-stu-id="290dc-120">The only supported type is MAPIOFFLINE_ADVISE_TYPE_STATECHANGE.</span></span>
    
<span data-ttu-id="290dc-121">_ulStateMask：_ 唯一受支持的状态是 MAPIOFFLINE_STATE_ALL。</span><span class="sxs-lookup"><span data-stu-id="290dc-121">_ulStateMask_: The only supported state is MAPIOFFLINE_STATE_ALL.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="290dc-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="290dc-122">See also</span></span>

- [<span data-ttu-id="290dc-123">IMAPIOfflineMgr::Advise</span><span class="sxs-lookup"><span data-stu-id="290dc-123">IMAPIOfflineMgr::Advise</span></span>](imapiofflinemgr-advise.md)
- [<span data-ttu-id="290dc-124">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="290dc-124">About the Offline State API</span></span>](about-the-offline-state-api.md) 
- [<span data-ttu-id="290dc-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="290dc-125">MAPI Constants</span></span>](mapi-constants.md) 
- [<span data-ttu-id="290dc-126">MAPIOFFLINE_CALLBACK_TYPE</span><span class="sxs-lookup"><span data-stu-id="290dc-126">MAPIOFFLINE_CALLBACK_TYPE</span></span>](mapioffline_callback_type.md)

