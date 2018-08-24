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
ms.openlocfilehash: 46c37dbcf1aa3b0469281b8db99f210bda0918be
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582299"
---
# <a name="ulrelease"></a><span data-ttu-id="82635-103">UlRelease</span><span class="sxs-lookup"><span data-stu-id="82635-103">UlRelease</span></span>

  
  
<span data-ttu-id="82635-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82635-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82635-105">提供一种方法来调用 OLE 方法**IUnknown::Release**。</span><span class="sxs-lookup"><span data-stu-id="82635-105">Provides an alternative way to invoke the OLE method **IUnknown::Release**.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="82635-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="82635-106">Header file:</span></span>  <br/> |<span data-ttu-id="82635-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="82635-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="82635-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="82635-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="82635-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="82635-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="82635-110">调用：</span><span class="sxs-lookup"><span data-stu-id="82635-110">Called by:</span></span>  <br/> |<span data-ttu-id="82635-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="82635-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG UlRelease(
  LPVOID punk
);
```

## <a name="parameters"></a><span data-ttu-id="82635-112">参数</span><span class="sxs-lookup"><span data-stu-id="82635-112">Parameters</span></span>

 <span data-ttu-id="82635-113">_punk_</span><span class="sxs-lookup"><span data-stu-id="82635-113">_punk_</span></span>
  
> <span data-ttu-id="82635-114">[in]从**IUnknown**接口，换句话说任何 MAPI 接口派生的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="82635-114">[in] Pointer to an interface derived from the **IUnknown** interface, in other words any MAPI interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="82635-115">返回值</span><span class="sxs-lookup"><span data-stu-id="82635-115">Return value</span></span>

<span data-ttu-id="82635-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="82635-116">S_OK</span></span> 
  
> <span data-ttu-id="82635-117">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="82635-117">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="82635-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="82635-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="82635-119">意外或未知的原点出现错误，无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="82635-119">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="82635-120">注解</span><span class="sxs-lookup"><span data-stu-id="82635-120">Remarks</span></span>

<span data-ttu-id="82635-121">引用计数是现有指向必须释放的对象数。</span><span class="sxs-lookup"><span data-stu-id="82635-121">The reference count is the number of existing pointers to the object to be released.</span></span> 
  
<span data-ttu-id="82635-122">如果_punk_参数为 NULL，则函数返回立即而无需调用**IUnknown::Release**</span><span class="sxs-lookup"><span data-stu-id="82635-122">If the  _punk_ parameter is NULL, the function returns immediately without calling **IUnknown::Release**</span></span>
  
 <span data-ttu-id="82635-123">**UlRelease**返回返回**IUnknown::Release**方法，该数据库可以等于必须释放的对象的引用计数的值。</span><span class="sxs-lookup"><span data-stu-id="82635-123">**UlRelease** returns the value returned by the **IUnknown::Release** method, which can be equal to the reference count for the object to be released.</span></span> 
  
<span data-ttu-id="82635-124">有关**IUnknown::Release**的详细信息，请参阅[实现 IUnknown 接口](implementing-the-iunknown-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="82635-124">For more information about **IUnknown::Release**, see [Implementing the IUnknown Interface](implementing-the-iunknown-interface.md).</span></span> 
  

