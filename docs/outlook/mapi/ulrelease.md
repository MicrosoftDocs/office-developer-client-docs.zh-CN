---
title: UlRelease
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlRelease
api_type:
- COM
ms.assetid: 95db96ef-f95f-41da-b216-f717c23bffd2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 288e34a159db48b1344524b87f02b045259f1565
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415843"
---
# <a name="ulrelease"></a><span data-ttu-id="ff811-103">UlRelease</span><span class="sxs-lookup"><span data-stu-id="ff811-103">UlRelease</span></span>

  
  
<span data-ttu-id="ff811-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff811-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff811-105">提供另一种调用 OLE 方法 **IUnknown：：Release 的方法**。</span><span class="sxs-lookup"><span data-stu-id="ff811-105">Provides an alternative way to invoke the OLE method **IUnknown::Release**.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ff811-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ff811-106">Header file:</span></span>  <br/> |<span data-ttu-id="ff811-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ff811-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="ff811-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="ff811-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ff811-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ff811-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ff811-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="ff811-110">Called by:</span></span>  <br/> |<span data-ttu-id="ff811-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="ff811-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG UlRelease(
  LPVOID punk
);
```

## <a name="parameters"></a><span data-ttu-id="ff811-112">参数</span><span class="sxs-lookup"><span data-stu-id="ff811-112">Parameters</span></span>

 <span data-ttu-id="ff811-113">_punk_</span><span class="sxs-lookup"><span data-stu-id="ff811-113">_punk_</span></span>
  
> <span data-ttu-id="ff811-114">[in]指向从 **IUnknown** 接口派生的接口的指针，即任何 MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="ff811-114">[in] Pointer to an interface derived from the **IUnknown** interface, in other words any MAPI interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ff811-115">返回值</span><span class="sxs-lookup"><span data-stu-id="ff811-115">Return value</span></span>

<span data-ttu-id="ff811-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff811-116">S_OK</span></span> 
  
> <span data-ttu-id="ff811-117">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="ff811-117">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="ff811-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="ff811-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="ff811-119">意外或未知来源的错误阻止了操作完成。</span><span class="sxs-lookup"><span data-stu-id="ff811-119">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ff811-120">备注</span><span class="sxs-lookup"><span data-stu-id="ff811-120">Remarks</span></span>

<span data-ttu-id="ff811-121">引用计数是指向要释放的对象的现有指针数。</span><span class="sxs-lookup"><span data-stu-id="ff811-121">The reference count is the number of existing pointers to the object to be released.</span></span> 
  
<span data-ttu-id="ff811-122">如果  _punk_ 参数为 NULL，函数将立即返回，而不调用 **IUnknown：：Release**</span><span class="sxs-lookup"><span data-stu-id="ff811-122">If the  _punk_ parameter is NULL, the function returns immediately without calling **IUnknown::Release**</span></span>
  
 <span data-ttu-id="ff811-123">**UlRelease** 返回 **IUnknown：：Release** 方法返回的值，该值可以等于要释放的对象的引用计数。</span><span class="sxs-lookup"><span data-stu-id="ff811-123">**UlRelease** returns the value returned by the **IUnknown::Release** method, which can be equal to the reference count for the object to be released.</span></span> 
  
<span data-ttu-id="ff811-124">有关 **IUnknown：：Release** 有关详细信息，请参阅 [实现 IUnknown 接口](implementing-the-iunknown-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="ff811-124">For more information about **IUnknown::Release**, see [Implementing the IUnknown Interface](implementing-the-iunknown-interface.md).</span></span> 
  

