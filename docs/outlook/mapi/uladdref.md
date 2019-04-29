---
title: UlAddRef
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlAddRef
api_type:
- COM
ms.assetid: 9b897cbc-90b2-4c60-b5f1-dc78e7e7952d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f9e55153830dbe41a2b4a48454157c900d96cf90
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432833"
---
# <a name="uladdref"></a><span data-ttu-id="e1aa3-103">UlAddRef</span><span class="sxs-lookup"><span data-stu-id="e1aa3-103">UlAddRef</span></span>

  
  
<span data-ttu-id="e1aa3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e1aa3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e1aa3-105">提供了调用 OLE 方法**IUnknown:: AddRef**的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="e1aa3-105">Provides an alternative way to invoke the OLE method **IUnknown::AddRef**.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e1aa3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="e1aa3-106">Header file:</span></span>  <br/> |<span data-ttu-id="e1aa3-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e1aa3-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="e1aa3-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="e1aa3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="e1aa3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="e1aa3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="e1aa3-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="e1aa3-110">Called by:</span></span>  <br/> |<span data-ttu-id="e1aa3-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="e1aa3-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG UlAddRef(
  LPVOID punk
);
```

## <a name="parameters"></a><span data-ttu-id="e1aa3-112">参数</span><span class="sxs-lookup"><span data-stu-id="e1aa3-112">Parameters</span></span>

 <span data-ttu-id="e1aa3-113">_punk_</span><span class="sxs-lookup"><span data-stu-id="e1aa3-113">_punk_</span></span>
  
> <span data-ttu-id="e1aa3-114">实时指向从**IUnknown**接口派生的接口的指针, 换句话说, 是任何 MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="e1aa3-114">[in] Pointer to an interface derived from the **IUnknown** interface, in other words any MAPI interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e1aa3-115">返回值</span><span class="sxs-lookup"><span data-stu-id="e1aa3-115">Return value</span></span>

<span data-ttu-id="e1aa3-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1aa3-116">S_OK</span></span> 
  
> <span data-ttu-id="e1aa3-117">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="e1aa3-117">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="e1aa3-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="e1aa3-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="e1aa3-119">意外或未知来源的错误阻止操作完成。</span><span class="sxs-lookup"><span data-stu-id="e1aa3-119">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e1aa3-120">说明</span><span class="sxs-lookup"><span data-stu-id="e1aa3-120">Remarks</span></span>

 <span data-ttu-id="e1aa3-121">**UlAddRef**返回由**IUnknown:: AddRef**方法返回的值, 它是接口的引用计数的新值。</span><span class="sxs-lookup"><span data-stu-id="e1aa3-121">**UlAddRef** returns the value returned by the **IUnknown::AddRef** method, which is the new value of the reference count for the interface.</span></span> <span data-ttu-id="e1aa3-122">值为非零值。</span><span class="sxs-lookup"><span data-stu-id="e1aa3-122">The value is nonzero.</span></span> 
  
<span data-ttu-id="e1aa3-123">有关**IUnknown:: AddRef**的详细信息, 请参阅[实现 IUnknown 接口](implementing-the-iunknown-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="e1aa3-123">For more information about **IUnknown::AddRef**, see [Implementing the IUnknown Interface](implementing-the-iunknown-interface.md).</span></span> 
  

