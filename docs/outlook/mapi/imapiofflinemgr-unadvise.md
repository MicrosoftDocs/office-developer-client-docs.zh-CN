---
title: IMAPIOfflineMgrUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineMgr.Unadvise
api_type:
- COM
ms.assetid: 250b9137-facb-81a2-41b1-96a57366c04e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b52dcd87c8714ad59db560a5ae4a8300f9cc83ae
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775500"
---
# <a name="imapiofflinemgrunadvise"></a><span data-ttu-id="70457-103">IMAPIOfflineMgr::Unadvise</span><span class="sxs-lookup"><span data-stu-id="70457-103">IMAPIOfflineMgr::Unadvise</span></span>

  
  
<span data-ttu-id="70457-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="70457-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="70457-105">取消脱机对象的回调。</span><span class="sxs-lookup"><span data-stu-id="70457-105">Cancels callbacks for an offline object.</span></span>
  
```cpp
HRESULT COfflineObj::Unadvise( 
      ULONG ulFlags, 
      ULONG ulAdviseToken 
);
```

## <a name="parameters"></a><span data-ttu-id="70457-106">参数</span><span class="sxs-lookup"><span data-stu-id="70457-106">Parameters</span></span>

 <span data-ttu-id="70457-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="70457-107">_ulFlags_</span></span>
  
> <span data-ttu-id="70457-108">[in]用于取消回调的标志。</span><span class="sxs-lookup"><span data-stu-id="70457-108">[in] Flags for canceling callback.</span></span> <span data-ttu-id="70457-109">支持仅值 MAPIOFFLINE_UNADVISE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="70457-109">Only the value MAPIOFFLINE_UNADVISE_DEFAULT is supported.</span></span>
    
 <span data-ttu-id="70457-110">_ulAdviseToken_</span><span class="sxs-lookup"><span data-stu-id="70457-110">_ulAdviseToken_</span></span>
  
> <span data-ttu-id="70457-111">[in]标识要取消此事件的回调注册 advise 令牌。</span><span class="sxs-lookup"><span data-stu-id="70457-111">[in] An advise token that identifies the callback registration that is to be canceled.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="70457-112">返回值</span><span class="sxs-lookup"><span data-stu-id="70457-112">Return value</span></span>

<span data-ttu-id="70457-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="70457-113">S_OK</span></span>
  
> <span data-ttu-id="70457-114">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="70457-114">The call was successful.</span></span> <span data-ttu-id="70457-115">此调用必须返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="70457-115">This call must return S_OK.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="70457-116">说明</span><span class="sxs-lookup"><span data-stu-id="70457-116">Remarks</span></span>

<span data-ttu-id="70457-117">删除回调与*ulAdviseToken*从以前调用**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 返回关联的注册。</span><span class="sxs-lookup"><span data-stu-id="70457-117">Removes the registration for the callback that was associated with  *ulAdviseToken*  returned from a prior call to **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> <span data-ttu-id="70457-118">导致**IMAPIOfflineMgr**对象来释放其上与*ulAdviseToken*关联的**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="70457-118">Causes the **IMAPIOfflineMgr** object to release its reference on the **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** object associated with  *ulAdviseToken*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="70457-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70457-119">See also</span></span>



[<span data-ttu-id="70457-120">IMAPIOfflineMgr::Advise</span><span class="sxs-lookup"><span data-stu-id="70457-120">IMAPIOfflineMgr::Advise</span></span>](imapiofflinemgr-advise.md)


[<span data-ttu-id="70457-121">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="70457-121">MAPI Constants</span></span>](mapi-constants.md)

