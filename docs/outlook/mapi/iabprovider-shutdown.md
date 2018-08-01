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
ms.openlocfilehash: 2f1872c6f95f8ab12014de9890b0d03789bc5f0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775236"
---
# <a name="iabprovidershutdown"></a><span data-ttu-id="1cc0b-103">IABProvider::Shutdown</span><span class="sxs-lookup"><span data-stu-id="1cc0b-103">IABProvider::Shutdown</span></span>

  
  
<span data-ttu-id="1cc0b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1cc0b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1cc0b-105">取消活动会话的连接。</span><span class="sxs-lookup"><span data-stu-id="1cc0b-105">Cancels a connection to an active session.</span></span>
  
```cpp
HRESULT Shutdown(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="1cc0b-106">参数</span><span class="sxs-lookup"><span data-stu-id="1cc0b-106">Parameters</span></span>

 <span data-ttu-id="1cc0b-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="1cc0b-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="1cc0b-108">[In]保留;必须为零的指针。</span><span class="sxs-lookup"><span data-stu-id="1cc0b-108">[In] Reserved; must be a pointer to zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1cc0b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1cc0b-109">Return value</span></span>

<span data-ttu-id="1cc0b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1cc0b-110">S_OK</span></span> 
  
> <span data-ttu-id="1cc0b-111">连接成功已取消。</span><span class="sxs-lookup"><span data-stu-id="1cc0b-111">The connection was successfully canceled.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="1cc0b-112">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="1cc0b-112">Notes to implementers</span></span>

<span data-ttu-id="1cc0b-113">**Shutdown**方法的实现中, 执行考虑所需的任何任务。</span><span class="sxs-lookup"><span data-stu-id="1cc0b-113">In your implementation of the **Shutdown** method, perform whatever tasks you consider necessary.</span></span> <span data-ttu-id="1cc0b-114">只有在已发布您的所有登录对象后，MAPI 调用**Shutdown**方法。</span><span class="sxs-lookup"><span data-stu-id="1cc0b-114">MAPI calls your **Shutdown** method only after you have released all your logon objects.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1cc0b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cc0b-115">See also</span></span>



[<span data-ttu-id="1cc0b-116">IABProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1cc0b-116">IABProvider : IUnknown</span></span>](iabprovideriunknown.md)

