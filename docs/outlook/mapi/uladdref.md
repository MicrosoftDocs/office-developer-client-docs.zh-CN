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
# <a name="uladdref"></a><span data-ttu-id="7e1d7-103">UlAddRef</span><span class="sxs-lookup"><span data-stu-id="7e1d7-103">UlAddRef</span></span>

  
  
<span data-ttu-id="7e1d7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7e1d7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7e1d7-105">提供另一种调用 OLE 方法 **IUnknown：：AddRef 的方法**。</span><span class="sxs-lookup"><span data-stu-id="7e1d7-105">Provides an alternative way to invoke the OLE method **IUnknown::AddRef**.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7e1d7-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7e1d7-106">Header file:</span></span>  <br/> |<span data-ttu-id="7e1d7-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7e1d7-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="7e1d7-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7e1d7-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7e1d7-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7e1d7-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7e1d7-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7e1d7-110">Called by:</span></span>  <br/> |<span data-ttu-id="7e1d7-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="7e1d7-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG UlAddRef(
  LPVOID punk
);
```

## <a name="parameters"></a><span data-ttu-id="7e1d7-112">参数</span><span class="sxs-lookup"><span data-stu-id="7e1d7-112">Parameters</span></span>

 <span data-ttu-id="7e1d7-113">_punk_</span><span class="sxs-lookup"><span data-stu-id="7e1d7-113">_punk_</span></span>
  
> <span data-ttu-id="7e1d7-114">[in]指向从 **IUnknown** 接口派生的接口的指针，即任何 MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="7e1d7-114">[in] Pointer to an interface derived from the **IUnknown** interface, in other words any MAPI interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7e1d7-115">返回值</span><span class="sxs-lookup"><span data-stu-id="7e1d7-115">Return value</span></span>

<span data-ttu-id="7e1d7-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e1d7-116">S_OK</span></span> 
  
> <span data-ttu-id="7e1d7-117">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="7e1d7-117">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="7e1d7-118">MAPI_E_CALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="7e1d7-118">MAPI_E_CALL_FAILED</span></span> 
  
> <span data-ttu-id="7e1d7-119">意外或未知来源的错误阻止了操作完成。</span><span class="sxs-lookup"><span data-stu-id="7e1d7-119">An error of unexpected or unknown origin prevented the operation from completing.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7e1d7-120">备注</span><span class="sxs-lookup"><span data-stu-id="7e1d7-120">Remarks</span></span>

 <span data-ttu-id="7e1d7-121">**UlAddRef** 返回 **IUnknown：：AddRef** 方法返回的值，这是接口的引用计数的新值。</span><span class="sxs-lookup"><span data-stu-id="7e1d7-121">**UlAddRef** returns the value returned by the **IUnknown::AddRef** method, which is the new value of the reference count for the interface.</span></span> <span data-ttu-id="7e1d7-122">该值为非零。</span><span class="sxs-lookup"><span data-stu-id="7e1d7-122">The value is nonzero.</span></span> 
  
<span data-ttu-id="7e1d7-123">有关 **IUnknown：：AddRef** 详细信息，请参阅 [实现 IUnknown 接口](implementing-the-iunknown-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="7e1d7-123">For more information about **IUnknown::AddRef**, see [Implementing the IUnknown Interface](implementing-the-iunknown-interface.md).</span></span> 
  

