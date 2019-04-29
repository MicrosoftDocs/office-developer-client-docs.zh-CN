---
title: CallUDF
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6421c9a2-07f7-4deb-aa43-c50d82cb0002
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 096f57335572c3788fdf129dd3bcf4a76cf62b01
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433008"
---
# <a name="calludf"></a><span data-ttu-id="c7317-103">CallUDF</span><span class="sxs-lookup"><span data-stu-id="c7317-103">CallUDF</span></span>

<span data-ttu-id="c7317-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7317-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c7317-105">在高性能计算环境中调用用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="c7317-105">Calls a user-defined function in a high-performance computing environment.</span></span>
  
```cpp
int CallUDF(int SessionId, WCHAR *XllName, WCHAR *UDFName, LPXLOPER12 pxAsyncHandle, int (*CallBackAddr)(), int ArgCount, LPXLOPER12 Parameter1, ...)
```

## <a name="parameters"></a><span data-ttu-id="c7317-106">参数</span><span class="sxs-lookup"><span data-stu-id="c7317-106">Parameters</span></span>

<span data-ttu-id="c7317-107">_SessionId_</span><span class="sxs-lookup"><span data-stu-id="c7317-107">_SessionId_</span></span>
  
> <span data-ttu-id="c7317-108">要在其中进行调用的会话的 ID。</span><span class="sxs-lookup"><span data-stu-id="c7317-108">The ID of the session in which to make the call.</span></span>
    
<span data-ttu-id="c7317-109">_XLLName_</span><span class="sxs-lookup"><span data-stu-id="c7317-109">_XLLName_</span></span>
  
> <span data-ttu-id="c7317-110">包含用户定义函数的 XLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="c7317-110">The name of the XLL that contains the user-defined function.</span></span>
    
<span data-ttu-id="c7317-111">_UDFName_</span><span class="sxs-lookup"><span data-stu-id="c7317-111">_UDFName_</span></span>
  
> <span data-ttu-id="c7317-112">用户定义的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="c7317-112">The name of the user-defined function.</span></span>
    
<span data-ttu-id="c7317-113">_CallBackAddr_</span><span class="sxs-lookup"><span data-stu-id="c7317-113">_CallBackAddr_</span></span>
  
> <span data-ttu-id="c7317-114">用户定义的函数完成时, 连接器应调用的函数。</span><span class="sxs-lookup"><span data-stu-id="c7317-114">The function that the connector should call when the user-defined function is finished.</span></span>
    
<span data-ttu-id="c7317-115">_pxAsyncHandle_</span><span class="sxs-lookup"><span data-stu-id="c7317-115">_pxAsyncHandle_</span></span>
  
> <span data-ttu-id="c7317-116">Excel 和连接器用来跟踪挂起的用户定义函数调用的异步句柄。</span><span class="sxs-lookup"><span data-stu-id="c7317-116">The asynchronous handle used by Excel and the connector to track the pending user-defined function call.</span></span> <span data-ttu-id="c7317-117">连接器在以后使用在_CallBackAddr_参数中传递的函数指针回调 Excel 时使用它。</span><span class="sxs-lookup"><span data-stu-id="c7317-117">The connector uses it later when the call is finished, when it calls back into Excel using the function pointer passed in the  _CallBackAddr_ argument.</span></span> 
    
<span data-ttu-id="c7317-118">_ArgCount_</span><span class="sxs-lookup"><span data-stu-id="c7317-118">_ArgCount_</span></span>
  
> <span data-ttu-id="c7317-119">要传递给用户定义函数的参数的数目。</span><span class="sxs-lookup"><span data-stu-id="c7317-119">The number of arguments to pass to the user-defined function.</span></span> <span data-ttu-id="c7317-120">允许的最大值为255。</span><span class="sxs-lookup"><span data-stu-id="c7317-120">The maximum value allowed is 255.</span></span>
    
<span data-ttu-id="c7317-121">_Parameter1_</span><span class="sxs-lookup"><span data-stu-id="c7317-121">_Parameter1_</span></span>
  
> <span data-ttu-id="c7317-122">要传递给用户定义的函数的值。</span><span class="sxs-lookup"><span data-stu-id="c7317-122">A value to pass to the user-defined function.</span></span> <span data-ttu-id="c7317-123">为_ArgCount_指示的每个参数重复此参数。</span><span class="sxs-lookup"><span data-stu-id="c7317-123">Repeat this argument for each parameter indicated by  _ArgCount_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c7317-124">返回值</span><span class="sxs-lookup"><span data-stu-id="c7317-124">Return value</span></span>

<span data-ttu-id="c7317-125">如果 UDF 调用已成功启动, 则为**xlHpcRetSuccess** 。**xlHpcRetInvalidSessionId**如果_SessionId_参数无效, 则为有关其他故障 (包括超时) 的**xlHpcRetCallFailed** 。如果调用返回任何错误代码 (除**xlHpcRetSuccess**之外的任何错误代码), 则 Excel 会认为 UDF 调用失败, 从而使_pxAsyncHandle_无效, 并且不希望发生回调。</span><span class="sxs-lookup"><span data-stu-id="c7317-125">**xlHpcRetSuccess** if the UDF call is successfully initiated; **xlHpcRetInvalidSessionId** if the  _SessionId_ argument is invalid; **xlHpcRetCallFailed** on other failures, including time-out. If the call returns any error code (anything except **xlHpcRetSuccess**), then Excel considers the UDF call to have failed, invalidates the  _pxAsyncHandle_, and does not expect a callback to occur.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c7317-126">说明</span><span class="sxs-lookup"><span data-stu-id="c7317-126">Remarks</span></span>

<span data-ttu-id="c7317-127">此函数以异步方式执行。</span><span class="sxs-lookup"><span data-stu-id="c7317-127">This function executes asynchronously.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c7317-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7317-128">See also</span></span>

- [<span data-ttu-id="c7317-129">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="c7317-129">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

