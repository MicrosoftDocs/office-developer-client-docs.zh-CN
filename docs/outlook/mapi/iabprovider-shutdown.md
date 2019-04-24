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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348900"
---
# <a name="iabprovidershutdown"></a><span data-ttu-id="9d567-103">IABProvider::Shutdown</span><span class="sxs-lookup"><span data-stu-id="9d567-103">IABProvider::Shutdown</span></span>

  
  
<span data-ttu-id="9d567-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9d567-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9d567-105">取消与活动会话的连接。</span><span class="sxs-lookup"><span data-stu-id="9d567-105">Cancels a connection to an active session.</span></span>
  
```cpp
HRESULT Shutdown(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="9d567-106">参数</span><span class="sxs-lookup"><span data-stu-id="9d567-106">Parameters</span></span>

 <span data-ttu-id="9d567-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="9d567-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="9d567-108">实时保留必须是指向零的指针。</span><span class="sxs-lookup"><span data-stu-id="9d567-108">[In] Reserved; must be a pointer to zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9d567-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9d567-109">Return value</span></span>

<span data-ttu-id="9d567-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d567-110">S_OK</span></span> 
  
> <span data-ttu-id="9d567-111">已成功取消连接。</span><span class="sxs-lookup"><span data-stu-id="9d567-111">The connection was successfully canceled.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="9d567-112">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="9d567-112">Notes to implementers</span></span>

<span data-ttu-id="9d567-113">在您的**Shutdown**方法实现中, 执行您认为必要的任何任务。</span><span class="sxs-lookup"><span data-stu-id="9d567-113">In your implementation of the **Shutdown** method, perform whatever tasks you consider necessary.</span></span> <span data-ttu-id="9d567-114">只有在发布了所有的登录对象之后, MAPI 才会调用您的**关闭**方法。</span><span class="sxs-lookup"><span data-stu-id="9d567-114">MAPI calls your **Shutdown** method only after you have released all your logon objects.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9d567-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d567-115">See also</span></span>



[<span data-ttu-id="9d567-116">IABProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9d567-116">IABProvider : IUnknown</span></span>](iabprovideriunknown.md)

