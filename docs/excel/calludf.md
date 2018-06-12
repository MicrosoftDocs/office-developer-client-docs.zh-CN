---
title: CallUDF
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6421c9a2-07f7-4deb-aa43-c50d82cb0002
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 1d55f22de88b274d0403f81717d0fddefbea0219
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773630"
---
# <a name="calludf"></a><span data-ttu-id="aa3d0-103">CallUDF</span><span class="sxs-lookup"><span data-stu-id="aa3d0-103">CallUDF</span></span>

<span data-ttu-id="aa3d0-104">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aa3d0-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="aa3d0-105">在高性能计算环境中调用用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-105">Calls a user-defined function in a high-performance computing environment.</span></span>
  
```cpp
int CallUDF(int SessionId, WCHAR *XllName, WCHAR *UDFName, LPXLOPER12 pxAsyncHandle, int (*CallBackAddr)(), int ArgCount, LPXLOPER12 Parameter1, ...)
```

## <a name="parameters"></a><span data-ttu-id="aa3d0-106">参数</span><span class="sxs-lookup"><span data-stu-id="aa3d0-106">Parameters</span></span>

<span data-ttu-id="aa3d0-107">_SessionId_</span><span class="sxs-lookup"><span data-stu-id="aa3d0-107">_SessionId_</span></span>
  
> <span data-ttu-id="aa3d0-108">要在其中进行呼叫的会话 ID。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-108">The ID of the session in which to make the call.</span></span>
    
<span data-ttu-id="aa3d0-109">_XLLName_</span><span class="sxs-lookup"><span data-stu-id="aa3d0-109">_XLLName_</span></span>
  
> <span data-ttu-id="aa3d0-110">包含用户定义函数的 XLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-110">The name of the XLL that contains the user-defined function.</span></span>
    
<span data-ttu-id="aa3d0-111">_UDFName_</span><span class="sxs-lookup"><span data-stu-id="aa3d0-111">_UDFName_</span></span>
  
> <span data-ttu-id="aa3d0-112">用户定义函数的名称。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-112">The name of the user-defined function.</span></span>
    
<span data-ttu-id="aa3d0-113">_CallBackAddr_</span><span class="sxs-lookup"><span data-stu-id="aa3d0-113">_CallBackAddr_</span></span>
  
> <span data-ttu-id="aa3d0-114">连接器应调用用户定义函数完成函数。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-114">The function that the connector should call when the user-defined function is finished.</span></span>
    
<span data-ttu-id="aa3d0-115">_pxAsyncHandle_</span><span class="sxs-lookup"><span data-stu-id="aa3d0-115">_pxAsyncHandle_</span></span>
  
> <span data-ttu-id="aa3d0-116">使用 Excel 和连接器以跟踪待处理的用户定义的函数调用异步句柄。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-116">The asynchronous handle used by Excel and the connector to track the pending user-defined function call.</span></span> <span data-ttu-id="aa3d0-117">连接器稍后使用完成呼叫后，当它回拨入 Excel 使用函数指针_CallBackAddr_参数中传递。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-117">The connector uses it later when the call is finished, when it calls back into Excel using the function pointer passed in the  _CallBackAddr_ argument.</span></span> 
    
<span data-ttu-id="aa3d0-118">_ArgCount_</span><span class="sxs-lookup"><span data-stu-id="aa3d0-118">_ArgCount_</span></span>
  
> <span data-ttu-id="aa3d0-119">要传递给的用户定义的函数的参数数目。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-119">The number of arguments to pass to the user-defined function.</span></span> <span data-ttu-id="aa3d0-120">允许的最大值是 255。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-120">The maximum value allowed is 255.</span></span>
    
<span data-ttu-id="aa3d0-121">_Parameter1_</span><span class="sxs-lookup"><span data-stu-id="aa3d0-121">_Parameter1_</span></span>
  
> <span data-ttu-id="aa3d0-122">要传递给的用户定义的函数值。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-122">A value to pass to the user-defined function.</span></span> <span data-ttu-id="aa3d0-123">重复的每个参数由_ArgCount_此参数。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-123">Repeat this argument for each parameter indicated by  _ArgCount_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="aa3d0-124">返回值</span><span class="sxs-lookup"><span data-stu-id="aa3d0-124">Return value</span></span>

<span data-ttu-id="aa3d0-125">**xlHpcRetSuccess** UDF 调用成功启动; 如果**xlHpcRetInvalidSessionId** _SessionId_参数无效; 如果在其他失败时，包括超时**xlHpcRetCallFailed** 。如果调用返回任何错误代码 （任何**xlHpcRetSuccess**除外），然后 Excel 认为已失败的 UDF 调用，使无效_pxAsyncHandle_，并不需要执行的回调。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-125">**xlHpcRetSuccess** if the UDF call is successfully initiated; **xlHpcRetInvalidSessionId** if the  _SessionId_ argument is invalid; **xlHpcRetCallFailed** on other failures, including time-out. If the call returns any error code (anything except **xlHpcRetSuccess**), then Excel considers the UDF call to have failed, invalidates the  _pxAsyncHandle_, and does not expect a callback to occur.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="aa3d0-126">备注</span><span class="sxs-lookup"><span data-stu-id="aa3d0-126">Remarks</span></span>

<span data-ttu-id="aa3d0-127">此函数异步执行。</span><span class="sxs-lookup"><span data-stu-id="aa3d0-127">This function executes asynchronously.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aa3d0-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa3d0-128">See also</span></span>

- [<span data-ttu-id="aa3d0-129">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="aa3d0-129">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

