---
title: xlRunningOnCluster
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
keywords:
- xlrunningoncluster
localization_priority: Normal
ms.assetid: 7662f255-4184-4af0-97f5-9a89347a201a
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f5c630c73899b07e2727a7d42b18eb1891797bab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310099"
---
# <a name="xlrunningoncluster"></a><span data-ttu-id="1c473-104">xlRunningOnCluster</span><span class="sxs-lookup"><span data-stu-id="1c473-104">xlRunningOnCluster</span></span>

<span data-ttu-id="1c473-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1c473-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="1c473-106">返回一个值, 该值指示用户定义的函数是否在群集上运行。</span><span class="sxs-lookup"><span data-stu-id="1c473-106">Returns a value that indicates whether the user-defined function is running on a cluster.</span></span> 
  
```cpp
Excel12(xlRunningOnCluster, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a><span data-ttu-id="1c473-107">参数</span><span class="sxs-lookup"><span data-stu-id="1c473-107">Parameters</span></span>

<span data-ttu-id="1c473-108">此函数没有参数。</span><span class="sxs-lookup"><span data-stu-id="1c473-108">This function has no arguments.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="1c473-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1c473-109">Return value</span></span>

<span data-ttu-id="1c473-110">如果函数在 Excel 进程中运行, 则在**xlTypeInt**类型的**XLOPER12**中返回0。</span><span class="sxs-lookup"><span data-stu-id="1c473-110">If the function is running in an Excel process, returns 0 in an **XLOPER12** of type **xlTypeInt**.</span></span> <span data-ttu-id="1c473-111">如果该函数在群集上运行, 则返回类型和值由群集连接器提供程序确定。</span><span class="sxs-lookup"><span data-stu-id="1c473-111">If the function is running on a cluster, the return type and value is determined by the cluster connector provider.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="1c473-112">Requirements</span><span class="sxs-lookup"><span data-stu-id="1c473-112">Requirements</span></span>

<span data-ttu-id="1c473-113">此函数是在 xlcall.h 头文件中定义的。</span><span class="sxs-lookup"><span data-stu-id="1c473-113">This function is defined in the Xlcall.h header file.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c473-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c473-114">See also</span></span>

- [<span data-ttu-id="1c473-115">群集安全函数</span><span class="sxs-lookup"><span data-stu-id="1c473-115">Cluster Safe Functions</span></span>](cluster-safe-functions.md)
- [<span data-ttu-id="1c473-116">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="1c473-116">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

