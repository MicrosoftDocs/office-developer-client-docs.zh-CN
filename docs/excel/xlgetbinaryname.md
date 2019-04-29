---
title: xlGetBinaryName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlGetBinaryName
keywords:
- xlgetbinaryname 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 66af3f78-65b5-42e0-82f9-ffd639d41751
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 6d063213e3f83451e8a072e71f0878174214f73e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412462"
---
# <a name="xlgetbinaryname"></a><span data-ttu-id="18f11-104">xlGetBinaryName</span><span class="sxs-lookup"><span data-stu-id="18f11-104">xlGetBinaryName</span></span>

<span data-ttu-id="18f11-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18f11-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="18f11-106">用于返回[xlDefineBinaryName 函数](xldefinebinaryname.md)所保存数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="18f11-106">Used to return a handle for data saved by the [xlDefineBinaryName function](xldefinebinaryname.md).</span></span> <span data-ttu-id="18f11-107">带有定义的二进制名称的数据将与工作簿一起保存, 并可在任何时候通过名称访问。</span><span class="sxs-lookup"><span data-stu-id="18f11-107">Data with a defined binary name is saved with the workbook and can be accessed by name at any time.</span></span> <span data-ttu-id="18f11-108">有关详细信息, 请参阅[Excel XLL 开发的已知问题](known-issues-in-excel-xll-development.md)中的 "二进制名称作用域限制"。</span><span class="sxs-lookup"><span data-stu-id="18f11-108">For more information, see "Binary name Scope Limitation" in [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
```cs
Excel12(xlGetBinaryName, LPXLOPER12 pxRes, 1, LPXLOPER12 pxName);
```

## <a name="parameters"></a><span data-ttu-id="18f11-109">参数</span><span class="sxs-lookup"><span data-stu-id="18f11-109">Parameters</span></span>

<span data-ttu-id="18f11-110">_pxRes_(**xltypeBigData**或**xltypeErr**)</span><span class="sxs-lookup"><span data-stu-id="18f11-110">_pxRes_ (**xltypeBigData** or **xltypeErr**)</span></span>
  
<span data-ttu-id="18f11-111">Bigdata 结构指定检索的数据或错误是无法检索数据, 或者未定义名称。</span><span class="sxs-lookup"><span data-stu-id="18f11-111">Bigdata structure specifying the retrieved data or an error is the data could not be retrieved or the name is not defined.</span></span> <span data-ttu-id="18f11-112">当函数返回时, **XLOPER**/ **XLOPER12**的**hdata**成员包含已命名数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="18f11-112">When the function returns, the **hdata** member of the **XLOPER**/ **XLOPER12** contains a handle for the named data.</span></span>  <span data-ttu-id="18f11-113">当不再需要时, 应在对**xlFree**的调用中释放_pxRes_ 。</span><span class="sxs-lookup"><span data-stu-id="18f11-113">_pxRes_ should be freed in a call to **xlFree** when no longer required.</span></span> 
  
<span data-ttu-id="18f11-114">_pxName_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="18f11-114">_pxName_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="18f11-115">一个指定数据的名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="18f11-115">A string specifying the name of the data.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="18f11-116">说明</span><span class="sxs-lookup"><span data-stu-id="18f11-116">Remarks</span></span>

<span data-ttu-id="18f11-117">Microsoft Excel 拥有在**hdata**中返回的内存句柄。</span><span class="sxs-lookup"><span data-stu-id="18f11-117">Microsoft Excel owns the memory handle returned in **hdata**.</span></span> <span data-ttu-id="18f11-118">在 Windows 中, 句柄是全局内存句柄 (由**GlobalAlloc**函数分配)。</span><span class="sxs-lookup"><span data-stu-id="18f11-118">In Windows, the handle is a global memory handle (allocated by the **GlobalAlloc** function).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="18f11-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18f11-119">See also</span></span>

- [<span data-ttu-id="18f11-120">xlDefineBinaryName</span><span class="sxs-lookup"><span data-stu-id="18f11-120">xlDefineBinaryName</span></span>](xldefinebinaryname.md)
- [<span data-ttu-id="18f11-121">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="18f11-121">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

