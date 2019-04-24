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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 800f79179f999ba193d4177abb7341095b8b896d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321215"
---
# <a name="imapiofflinemgrunadvise"></a><span data-ttu-id="64716-103">IMAPIOfflineMgr::Unadvise</span><span class="sxs-lookup"><span data-stu-id="64716-103">IMAPIOfflineMgr::Unadvise</span></span>

  
  
<span data-ttu-id="64716-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64716-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="64716-105">取消对脱机对象的回调。</span><span class="sxs-lookup"><span data-stu-id="64716-105">Cancels callbacks for an offline object.</span></span>
  
```cpp
HRESULT COfflineObj::Unadvise( 
      ULONG ulFlags, 
      ULONG ulAdviseToken 
);
```

## <a name="parameters"></a><span data-ttu-id="64716-106">参数</span><span class="sxs-lookup"><span data-stu-id="64716-106">Parameters</span></span>

 <span data-ttu-id="64716-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="64716-107">_ulFlags_</span></span>
  
> <span data-ttu-id="64716-108">实时用于取消回调的标志。</span><span class="sxs-lookup"><span data-stu-id="64716-108">[in] Flags for canceling callback.</span></span> <span data-ttu-id="64716-109">仅支持值 MAPIOFFLINE_UNADVISE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="64716-109">Only the value MAPIOFFLINE_UNADVISE_DEFAULT is supported.</span></span>
    
 <span data-ttu-id="64716-110">_ulAdviseToken_</span><span class="sxs-lookup"><span data-stu-id="64716-110">_ulAdviseToken_</span></span>
  
> <span data-ttu-id="64716-111">实时一个建议令牌, 用于标识要取消的回调注册。</span><span class="sxs-lookup"><span data-stu-id="64716-111">[in] An advise token that identifies the callback registration that is to be canceled.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="64716-112">返回值</span><span class="sxs-lookup"><span data-stu-id="64716-112">Return value</span></span>

<span data-ttu-id="64716-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="64716-113">S_OK</span></span>
  
> <span data-ttu-id="64716-114">调用成功。</span><span class="sxs-lookup"><span data-stu-id="64716-114">The call was successful.</span></span> <span data-ttu-id="64716-115">此调用必须返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="64716-115">This call must return S_OK.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="64716-116">注解</span><span class="sxs-lookup"><span data-stu-id="64716-116">Remarks</span></span>

<span data-ttu-id="64716-117">删除与*ulAdviseToken*相关联的回调的注册, 该回调是从以前对**[IMAPIOfflineMgr:: 建议](imapiofflinemgr-advise.md)** 的调用返回的。</span><span class="sxs-lookup"><span data-stu-id="64716-117">Removes the registration for the callback that was associated with  *ulAdviseToken*  returned from a prior call to **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> <span data-ttu-id="64716-118">使**IMAPIOfflineMgr**对象释放其对与*ulAdviseToken*相关联的**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="64716-118">Causes the **IMAPIOfflineMgr** object to release its reference on the **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** object associated with  *ulAdviseToken*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="64716-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64716-119">See also</span></span>



[<span data-ttu-id="64716-120">IMAPIOfflineMgr::Advise</span><span class="sxs-lookup"><span data-stu-id="64716-120">IMAPIOfflineMgr::Advise</span></span>](imapiofflinemgr-advise.md)


[<span data-ttu-id="64716-121">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="64716-121">MAPI Constants</span></span>](mapi-constants.md)

