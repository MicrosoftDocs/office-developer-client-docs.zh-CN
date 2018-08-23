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
ms.openlocfilehash: 35dfc7af9852609dcfcc3fcb9d65ec2e4afa9632
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579520"
---
# <a name="imapiofflinemgrunadvise"></a><span data-ttu-id="5775f-103">IMAPIOfflineMgr::Unadvise</span><span class="sxs-lookup"><span data-stu-id="5775f-103">IMAPIOfflineMgr::Unadvise</span></span>

  
  
<span data-ttu-id="5775f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5775f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5775f-105">取消脱机对象的回调。</span><span class="sxs-lookup"><span data-stu-id="5775f-105">Cancels callbacks for an offline object.</span></span>
  
```cpp
HRESULT COfflineObj::Unadvise( 
      ULONG ulFlags, 
      ULONG ulAdviseToken 
);
```

## <a name="parameters"></a><span data-ttu-id="5775f-106">参数</span><span class="sxs-lookup"><span data-stu-id="5775f-106">Parameters</span></span>

 <span data-ttu-id="5775f-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5775f-107">_ulFlags_</span></span>
  
> <span data-ttu-id="5775f-108">[in]用于取消回调的标志。</span><span class="sxs-lookup"><span data-stu-id="5775f-108">[in] Flags for canceling callback.</span></span> <span data-ttu-id="5775f-109">支持仅值 MAPIOFFLINE_UNADVISE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="5775f-109">Only the value MAPIOFFLINE_UNADVISE_DEFAULT is supported.</span></span>
    
 <span data-ttu-id="5775f-110">_ulAdviseToken_</span><span class="sxs-lookup"><span data-stu-id="5775f-110">_ulAdviseToken_</span></span>
  
> <span data-ttu-id="5775f-111">[in]标识要取消此事件的回调注册 advise 令牌。</span><span class="sxs-lookup"><span data-stu-id="5775f-111">[in] An advise token that identifies the callback registration that is to be canceled.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5775f-112">返回值</span><span class="sxs-lookup"><span data-stu-id="5775f-112">Return value</span></span>

<span data-ttu-id="5775f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5775f-113">S_OK</span></span>
  
> <span data-ttu-id="5775f-114">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="5775f-114">The call was successful.</span></span> <span data-ttu-id="5775f-115">此调用必须返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="5775f-115">This call must return S_OK.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5775f-116">注解</span><span class="sxs-lookup"><span data-stu-id="5775f-116">Remarks</span></span>

<span data-ttu-id="5775f-117">删除回调与*ulAdviseToken*从以前调用**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 返回关联的注册。</span><span class="sxs-lookup"><span data-stu-id="5775f-117">Removes the registration for the callback that was associated with  *ulAdviseToken*  returned from a prior call to **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> <span data-ttu-id="5775f-118">导致**IMAPIOfflineMgr**对象来释放其上与*ulAdviseToken*关联的**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="5775f-118">Causes the **IMAPIOfflineMgr** object to release its reference on the **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** object associated with  *ulAdviseToken*  .</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5775f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5775f-119">See also</span></span>



[<span data-ttu-id="5775f-120">IMAPIOfflineMgr::Advise</span><span class="sxs-lookup"><span data-stu-id="5775f-120">IMAPIOfflineMgr::Advise</span></span>](imapiofflinemgr-advise.md)


[<span data-ttu-id="5775f-121">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="5775f-121">MAPI Constants</span></span>](mapi-constants.md)

