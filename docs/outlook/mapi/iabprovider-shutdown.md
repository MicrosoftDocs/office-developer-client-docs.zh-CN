---
title: IABProviderShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABProvider.Shutdown
api_type:
- COM
ms.assetid: 1fbe6dc1-254b-4557-92c8-9fa42a8efd64
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8b2190f77c7575d3d4f5e25fa0863bec844158bc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409781"
---
# <a name="iabprovidershutdown"></a><span data-ttu-id="97578-103">IABProvider::Shutdown</span><span class="sxs-lookup"><span data-stu-id="97578-103">IABProvider::Shutdown</span></span>

  
  
<span data-ttu-id="97578-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="97578-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="97578-105">取消与活动会话的连接。</span><span class="sxs-lookup"><span data-stu-id="97578-105">Cancels a connection to an active session.</span></span>
  
```cpp
HRESULT Shutdown(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="97578-106">参数</span><span class="sxs-lookup"><span data-stu-id="97578-106">Parameters</span></span>

 <span data-ttu-id="97578-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="97578-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="97578-108">[In]保留;必须是指向零的指针。</span><span class="sxs-lookup"><span data-stu-id="97578-108">[In] Reserved; must be a pointer to zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="97578-109">返回值</span><span class="sxs-lookup"><span data-stu-id="97578-109">Return value</span></span>

<span data-ttu-id="97578-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="97578-110">S_OK</span></span> 
  
> <span data-ttu-id="97578-111">连接已成功取消。</span><span class="sxs-lookup"><span data-stu-id="97578-111">The connection was successfully canceled.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="97578-112">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="97578-112">Notes to implementers</span></span>

<span data-ttu-id="97578-113">在 Shutdown 方法 **的实现** 中，执行你认为必要的任何任务。</span><span class="sxs-lookup"><span data-stu-id="97578-113">In your implementation of the **Shutdown** method, perform whatever tasks you consider necessary.</span></span> <span data-ttu-id="97578-114">MAPI **仅在释放** 所有登录对象后调用 Shutdown 方法。</span><span class="sxs-lookup"><span data-stu-id="97578-114">MAPI calls your **Shutdown** method only after you have released all your logon objects.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="97578-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97578-115">See also</span></span>



[<span data-ttu-id="97578-116">IABProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="97578-116">IABProvider : IUnknown</span></span>](iabprovideriunknown.md)

