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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0a93dd44960a01996672a55501a7626d0ff56986
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567886"
---
# <a name="iabprovidershutdown"></a><span data-ttu-id="ad3d9-103">IABProvider::Shutdown</span><span class="sxs-lookup"><span data-stu-id="ad3d9-103">IABProvider::Shutdown</span></span>

  
  
<span data-ttu-id="ad3d9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ad3d9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ad3d9-105">取消活动会话的连接。</span><span class="sxs-lookup"><span data-stu-id="ad3d9-105">Cancels a connection to an active session.</span></span>
  
```cpp
HRESULT Shutdown(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="ad3d9-106">参数</span><span class="sxs-lookup"><span data-stu-id="ad3d9-106">Parameters</span></span>

 <span data-ttu-id="ad3d9-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="ad3d9-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="ad3d9-108">[In]保留;必须为零的指针。</span><span class="sxs-lookup"><span data-stu-id="ad3d9-108">[In] Reserved; must be a pointer to zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ad3d9-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ad3d9-109">Return value</span></span>

<span data-ttu-id="ad3d9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad3d9-110">S_OK</span></span> 
  
> <span data-ttu-id="ad3d9-111">连接成功已取消。</span><span class="sxs-lookup"><span data-stu-id="ad3d9-111">The connection was successfully canceled.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="ad3d9-112">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="ad3d9-112">Notes to implementers</span></span>

<span data-ttu-id="ad3d9-113">**Shutdown**方法的实现中, 执行考虑所需的任何任务。</span><span class="sxs-lookup"><span data-stu-id="ad3d9-113">In your implementation of the **Shutdown** method, perform whatever tasks you consider necessary.</span></span> <span data-ttu-id="ad3d9-114">只有在已发布您的所有登录对象后，MAPI 调用**Shutdown**方法。</span><span class="sxs-lookup"><span data-stu-id="ad3d9-114">MAPI calls your **Shutdown** method only after you have released all your logon objects.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ad3d9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad3d9-115">See also</span></span>



[<span data-ttu-id="ad3d9-116">IABProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ad3d9-116">IABProvider : IUnknown</span></span>](iabprovideriunknown.md)

