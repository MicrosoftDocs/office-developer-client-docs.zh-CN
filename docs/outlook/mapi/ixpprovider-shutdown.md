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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357195"
---
# <a name="ixpprovidershutdown"></a><span data-ttu-id="bb928-103">IXPProvider::Shutdown</span><span class="sxs-lookup"><span data-stu-id="bb928-103">IXPProvider::Shutdown</span></span>

  
  
<span data-ttu-id="bb928-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb928-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bb928-105">以有序的方式关闭传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="bb928-105">Closes down a transport provider in an orderly fashion.</span></span>
  
```cpp
HRESULT Shutdown (
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="bb928-106">参数</span><span class="sxs-lookup"><span data-stu-id="bb928-106">Parameters</span></span>

 <span data-ttu-id="bb928-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="bb928-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="bb928-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="bb928-108">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bb928-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bb928-109">Return value</span></span>

<span data-ttu-id="bb928-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb928-110">S_OK</span></span> 
  
> <span data-ttu-id="bb928-111">调用成功关闭了传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="bb928-111">The call succeeded in shutting down the transport provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bb928-112">注解</span><span class="sxs-lookup"><span data-stu-id="bb928-112">Remarks</span></span>

<span data-ttu-id="bb928-113">MAPI 后台处理程序在释放传输提供程序对象之前, 先调用**IXPProvider:: Shutdown**方法。</span><span class="sxs-lookup"><span data-stu-id="bb928-113">The MAPI spooler calls the **IXPProvider::Shutdown** method just prior to releasing a transport provider object.</span></span> <span data-ttu-id="bb928-114">在呼叫**关闭**之前, MAPI 将释放所有登录对象的提供程序。</span><span class="sxs-lookup"><span data-stu-id="bb928-114">Before calling **Shutdown**, MAPI releases all logon objects for a provider.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bb928-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb928-115">See also</span></span>



[<span data-ttu-id="bb928-116">XPProviderInit</span><span class="sxs-lookup"><span data-stu-id="bb928-116">XPProviderInit</span></span>](xpproviderinit.md)
  
[<span data-ttu-id="bb928-117">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bb928-117">IXPProvider : IUnknown</span></span>](ixpprovideriunknown.md)

