---
title: IXPProviderShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPProvider.Shutdown
api_type:
- COM
ms.assetid: e2d8a025-c2a3-4edb-b6e4-022e07e854dd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f5d253d0306e55699fbe5b9c9decf8c3242867fd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776133"
---
# <a name="ixpprovidershutdown"></a><span data-ttu-id="c34bf-103">IXPProvider::Shutdown</span><span class="sxs-lookup"><span data-stu-id="c34bf-103">IXPProvider::Shutdown</span></span>

  
  
<span data-ttu-id="c34bf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c34bf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c34bf-105">传输提供程序中有序的方式将关闭。</span><span class="sxs-lookup"><span data-stu-id="c34bf-105">Closes down a transport provider in an orderly fashion.</span></span>
  
```cpp
HRESULT Shutdown (
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="c34bf-106">参数</span><span class="sxs-lookup"><span data-stu-id="c34bf-106">Parameters</span></span>

 <span data-ttu-id="c34bf-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="c34bf-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="c34bf-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="c34bf-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c34bf-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c34bf-109">Return value</span></span>

<span data-ttu-id="c34bf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c34bf-110">S_OK</span></span> 
  
> <span data-ttu-id="c34bf-111">呼叫已成功关闭传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="c34bf-111">The call succeeded in shutting down the transport provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c34bf-112">说明</span><span class="sxs-lookup"><span data-stu-id="c34bf-112">Remarks</span></span>

<span data-ttu-id="c34bf-113">MAPI 后台处理程序调用**IXPProvider::Shutdown**方法只之前释放传输提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="c34bf-113">The MAPI spooler calls the **IXPProvider::Shutdown** method just prior to releasing a transport provider object.</span></span> <span data-ttu-id="c34bf-114">调用之前**关闭**，MAPI 提供程序释放所有登录对象。</span><span class="sxs-lookup"><span data-stu-id="c34bf-114">Before calling **Shutdown**, MAPI releases all logon objects for a provider.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c34bf-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c34bf-115">See also</span></span>



[<span data-ttu-id="c34bf-116">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="c34bf-116">XPProviderInit</span></span>](xpproviderinit.md)
  
[<span data-ttu-id="c34bf-117">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c34bf-117">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)

