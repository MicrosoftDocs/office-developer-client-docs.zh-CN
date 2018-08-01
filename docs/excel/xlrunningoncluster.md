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
ms.openlocfilehash: f42ccbeb94e1fc6b6cf880f1b32ee1bfeb24997e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773878"
---
# <a name="xlrunningoncluster"></a><span data-ttu-id="2e30a-104">xlRunningOnCluster</span><span class="sxs-lookup"><span data-stu-id="2e30a-104">xlRunningOnCluster</span></span>

<span data-ttu-id="2e30a-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e30a-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2e30a-106">返回一个值，该值指示是否在群集上运行的用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="2e30a-106">Returns a value that indicates whether the user-defined function is running on a cluster.</span></span> 
  
```cpp
Excel12(xlRunningOnCluster, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a><span data-ttu-id="2e30a-107">参数</span><span class="sxs-lookup"><span data-stu-id="2e30a-107">Parameters</span></span>

<span data-ttu-id="2e30a-108">此函数具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="2e30a-108">This function has no arguments.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="2e30a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2e30a-109">Return value</span></span>

<span data-ttu-id="2e30a-110">如果在函数 Excel 进程中运行，在类型**xlTypeInt** **XLOPER12**返回 0。</span><span class="sxs-lookup"><span data-stu-id="2e30a-110">If the function is running in an Excel process, returns 0 in an **XLOPER12** of type **xlTypeInt**.</span></span> <span data-ttu-id="2e30a-111">如果在函数在群集上运行，由群集连接器提供程序确定的返回类型和值。</span><span class="sxs-lookup"><span data-stu-id="2e30a-111">If the function is running on a cluster, the return type and value is determined by the cluster connector provider.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="2e30a-112">要求</span><span class="sxs-lookup"><span data-stu-id="2e30a-112">Requirements</span></span>

<span data-ttu-id="2e30a-113">Xlcall.h 头文件中定义此函数。</span><span class="sxs-lookup"><span data-stu-id="2e30a-113">This function is defined in the Xlcall.h header file.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e30a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e30a-114">See also</span></span>

- [<span data-ttu-id="2e30a-115">群集安全函数</span><span class="sxs-lookup"><span data-stu-id="2e30a-115">Cluster Safe Functions</span></span>](cluster-safe-functions.md)
- [<span data-ttu-id="2e30a-116">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="2e30a-116">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

