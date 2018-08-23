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
ms.openlocfilehash: baf45fa33ca085f51a6f9c20f72ec1fd1545ad79
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592368"
---
# <a name="uladdref"></a><span data-ttu-id="2f62e-103">UlAddRef</span><span class="sxs-lookup"><span data-stu-id="2f62e-103">UlAddRef</span></span>

  
  
<span data-ttu-id="2f62e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f62e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f62e-105">提供一种方法来调用 OLE 方法**IUnknown::AddRef**。</span><span class="sxs-lookup"><span data-stu-id="2f62e-105">Provides an alternative way to invoke the OLE method **IUnknown::AddRef**.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2f62e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2f62e-106">Header file:</span></span>  <br/> |<span data-ttu-id="2f62e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2f62e-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="2f62e-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2f62e-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="2f62e-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="2f62e-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="2f62e-110">调用：</span><span class="sxs-lookup"><span data-stu-id="2f62e-110">Called by:</span></span>  <br/> |<span data-ttu-id="2f62e-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="2f62e-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG UlAddRef(
  LPVOID punk
);
```

## <a name="parameters"></a><span data-ttu-id="2f62e-112">参数</span><span class="sxs-lookup"><span data-stu-id="2f62e-112">Parameters</span></span>

 <span data-ttu-id="2f62e-113">_punk_</span><span class="sxs-lookup"><span data-stu-id="2f62e-113">_punk_</span></span>
  
> <span data-ttu-id="2f62e-114">[in]从**IUnknown**接口，换句话说任何 MAPI 接口派生的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2f62e-114">[in] Pointer to an interface derived from the **IUnknown** interface, in other words any MAPI interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2f62e-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2f62e-115">Return value</span></span>

<span data-ttu-id="2f62e-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f62e-116">S_OK</span></span> 
  
> <span data-ttu-id="2f62e-117">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="2f62e-117">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="2f62e-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="2f62e-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="2f62e-119">意外或未知的原点出现错误，无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="2f62e-119">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2f62e-120">注解</span><span class="sxs-lookup"><span data-stu-id="2f62e-120">Remarks</span></span>

 <span data-ttu-id="2f62e-121">**UlAddRef**返回**IUnknown::AddRef**方法，这是新的接口的引用计数值返回的值。</span><span class="sxs-lookup"><span data-stu-id="2f62e-121">**UlAddRef** returns the value returned by the **IUnknown::AddRef** method, which is the new value of the reference count for the interface.</span></span> <span data-ttu-id="2f62e-122">值为非零值。</span><span class="sxs-lookup"><span data-stu-id="2f62e-122">The value is nonzero.</span></span> 
  
<span data-ttu-id="2f62e-123">有关**IUnknown::AddRef**的详细信息，请参阅[实现 IUnknown 接口](implementing-the-iunknown-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="2f62e-123">For more information about **IUnknown::AddRef**, see [Implementing the IUnknown Interface](implementing-the-iunknown-interface.md).</span></span> 
  

