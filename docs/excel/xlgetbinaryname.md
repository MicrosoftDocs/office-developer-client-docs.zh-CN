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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d2332967e798b43a350c0733cd7398e2a921add6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773847"
---
# <a name="xlgetbinaryname"></a><span data-ttu-id="0aa67-104">xlGetBinaryName</span><span class="sxs-lookup"><span data-stu-id="0aa67-104">xlGetBinaryName</span></span>

<span data-ttu-id="0aa67-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0aa67-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="0aa67-106">用于返回[xlDefineBinaryName 函数](xldefinebinaryname.md)保存数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="0aa67-106">Used to return a handle for data saved by the [xlDefineBinaryName function](xldefinebinaryname.md).</span></span> <span data-ttu-id="0aa67-107">数据定义二进制文件名称保存在工作薄和随时都可以通过名称访问。</span><span class="sxs-lookup"><span data-stu-id="0aa67-107">Data with a defined binary name is saved with the workbook and can be accessed by name at any time.</span></span> <span data-ttu-id="0aa67-108">有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中的"二进制命名范围限制"。</span><span class="sxs-lookup"><span data-stu-id="0aa67-108">For more information, see "Binary name Scope Limitation" in [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
```cs
Excel12(xlGetBinaryName, LPXLOPER12 pxRes, 1, LPXLOPER12 pxName);
```

## <a name="parameters"></a><span data-ttu-id="0aa67-109">参数</span><span class="sxs-lookup"><span data-stu-id="0aa67-109">Parameters</span></span>

<span data-ttu-id="0aa67-110">_pxRes_（**xltypeBigData**或**xltypeErr**）</span><span class="sxs-lookup"><span data-stu-id="0aa67-110">_pxRes_ (**xltypeBigData** or **xltypeErr**)</span></span>
  
<span data-ttu-id="0aa67-111">无法检索 Bigdata 结构指定检索到的数据或错误数据或未定义名称。</span><span class="sxs-lookup"><span data-stu-id="0aa67-111">Bigdata structure specifying the retrieved data or an error is the data could not be retrieved or the name is not defined.</span></span> <span data-ttu-id="0aa67-112">当函数返回时， **XLOPER**的**hdata**成员/ **XLOPER12**包含已命名的数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="0aa67-112">When the function returns, the **hdata** member of the **XLOPER**/ **XLOPER12** contains a handle for the named data.</span></span>  <span data-ttu-id="0aa67-113">_pxRes_应释放**xlFree**当不再需要时将调用。</span><span class="sxs-lookup"><span data-stu-id="0aa67-113">_pxRes_ should be freed in a call to **xlFree** when no longer required.</span></span> 
  
<span data-ttu-id="0aa67-114">_pxName_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="0aa67-114">_pxName_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="0aa67-115">指定的数据的名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="0aa67-115">A string specifying the name of the data.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0aa67-116">说明</span><span class="sxs-lookup"><span data-stu-id="0aa67-116">Remarks</span></span>

<span data-ttu-id="0aa67-117">Microsoft Excel 拥有**hdata**中返回的内存句柄。</span><span class="sxs-lookup"><span data-stu-id="0aa67-117">Microsoft Excel owns the memory handle returned in **hdata**.</span></span> <span data-ttu-id="0aa67-118">在 Windows 中，句柄是 （分配**GlobalAlloc**函数） 的全局内存句柄。</span><span class="sxs-lookup"><span data-stu-id="0aa67-118">In Windows, the handle is a global memory handle (allocated by the **GlobalAlloc** function).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0aa67-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0aa67-119">See also</span></span>

- [<span data-ttu-id="0aa67-120">xlDefineBinaryName</span><span class="sxs-lookup"><span data-stu-id="0aa67-120">xlDefineBinaryName</span></span>](xldefinebinaryname.md)
- [<span data-ttu-id="0aa67-121">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="0aa67-121">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

