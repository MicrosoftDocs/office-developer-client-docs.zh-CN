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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a57a72b413ba412154a27a08244e86b117cbea7d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409690"
---
# <a name="ixpprovidershutdown"></a><span data-ttu-id="80028-103">IXPProvider::Shutdown</span><span class="sxs-lookup"><span data-stu-id="80028-103">IXPProvider::Shutdown</span></span>

  
  
<span data-ttu-id="80028-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="80028-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="80028-105">以有序方式关闭传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="80028-105">Closes down a transport provider in an orderly fashion.</span></span>
  
```cpp
HRESULT Shutdown (
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="80028-106">参数</span><span class="sxs-lookup"><span data-stu-id="80028-106">Parameters</span></span>

 <span data-ttu-id="80028-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="80028-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="80028-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="80028-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="80028-109">返回值</span><span class="sxs-lookup"><span data-stu-id="80028-109">Return value</span></span>

<span data-ttu-id="80028-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="80028-110">S_OK</span></span> 
  
> <span data-ttu-id="80028-111">呼叫成功关闭传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="80028-111">The call succeeded in shutting down the transport provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="80028-112">备注</span><span class="sxs-lookup"><span data-stu-id="80028-112">Remarks</span></span>

<span data-ttu-id="80028-113">MAPI 后台处理程序在释放传输提供程序对象之前调用 **IXPProvider：：Shutdown** 方法。</span><span class="sxs-lookup"><span data-stu-id="80028-113">The MAPI spooler calls the **IXPProvider::Shutdown** method just prior to releasing a transport provider object.</span></span> <span data-ttu-id="80028-114">在调用 **Shutdown** 之前，MAPI 会释放提供程序的所有登录对象。</span><span class="sxs-lookup"><span data-stu-id="80028-114">Before calling **Shutdown**, MAPI releases all logon objects for a provider.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="80028-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80028-115">See also</span></span>



[<span data-ttu-id="80028-116">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="80028-116">XPProviderInit</span></span>](xpproviderinit.md)
  
[<span data-ttu-id="80028-117">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="80028-117">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)

