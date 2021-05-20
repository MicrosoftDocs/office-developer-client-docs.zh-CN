---
title: xlDefineBinaryName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlDefineBinaryName
keywords:
- xldefinebinaryname 函数 [excel 2007]
localization_priority: Normal
ms.assetid: e3e8f91b-cc31-4f09-9941-f950ae96820a
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3c7fc4f6b6fc7179c1ca84043895273b2781f8b5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430250"
---
# <a name="xldefinebinaryname"></a><span data-ttu-id="d0a60-104">xlDefineBinaryName</span><span class="sxs-lookup"><span data-stu-id="d0a60-104">xlDefineBinaryName</span></span>

 <span data-ttu-id="d0a60-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d0a60-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d0a60-106">用于为 **xltypeBigData** **XLOPER** /  **XLOPER12 分配永久性存储**。</span><span class="sxs-lookup"><span data-stu-id="d0a60-106">Used to allocate persistent storage for an **xltypeBigData** **XLOPER**/ **XLOPER12**.</span></span> <span data-ttu-id="d0a60-107">具有定义的二进制名称的数据随工作簿一起保存，并且随时都可以按名称访问。</span><span class="sxs-lookup"><span data-stu-id="d0a60-107">Data with a defined binary name is saved with the workbook, and can be accessed by name at any time.</span></span> <span data-ttu-id="d0a60-108">有关详细信息，请参阅 XLL 开发中的已知问题中的"二Excel[范围限制"。](known-issues-in-excel-xll-development.md)</span><span class="sxs-lookup"><span data-stu-id="d0a60-108">For more information, see "Binary Name Scope Limitation" in [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
```cs
Excel12(xlDefineBinaryName, 0, 2, LPXLOPER12 pxName, LPXLOPER12 pxData);
```

## <a name="parameters"></a><span data-ttu-id="d0a60-109">参数</span><span class="sxs-lookup"><span data-stu-id="d0a60-109">Parameters</span></span>

 <span data-ttu-id="d0a60-110">_pxName_ (**xltypeStr**) </span><span class="sxs-lookup"><span data-stu-id="d0a60-110">_pxName_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="d0a60-111">指定数据名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0a60-111">A string specifying the name of the data.</span></span> <span data-ttu-id="d0a60-112">字符串受与已定义名称相同的命名限制约束。</span><span class="sxs-lookup"><span data-stu-id="d0a60-112">The string is subject to the same naming restrictions as defined names.</span></span>
  
 <span data-ttu-id="d0a60-113">_pxData_ (**xltypeBigData**) </span><span class="sxs-lookup"><span data-stu-id="d0a60-113">_pxData_ (**xltypeBigData**)</span></span>
  
<span data-ttu-id="d0a60-114">用于指定要存储数据的 Bigdata 结构。</span><span class="sxs-lookup"><span data-stu-id="d0a60-114">Bigdata structure specifying the data to be stored.</span></span> <span data-ttu-id="d0a60-115">调用此函数时 **，bigdata** 结构的 **lpbData** 成员应指向要定义其名称的数据 **，cbData** 成员应包含数据的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d0a60-115">When you call this function, the **lpbData** member of the **bigdata** structure should point to the data for which the name is being defined, and the **cbData** member should contain the length of the data in bytes.</span></span> 
  
<span data-ttu-id="d0a60-116">如果在 **xltypeMissing** (未指定 _pxData_ 参数) _pxName_ 指定的已命名分配将被删除。</span><span class="sxs-lookup"><span data-stu-id="d0a60-116">If the  _pxData_ argument is not specified (**xltypeMissing**), the named allocation specified by  _pxName_ is deleted.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d0a60-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0a60-117">See also</span></span>



[<span data-ttu-id="d0a60-118">xlGetBinaryName</span><span class="sxs-lookup"><span data-stu-id="d0a60-118">xlGetBinaryName</span></span>](xlgetbinaryname.md)


[<span data-ttu-id="d0a60-119">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="d0a60-119">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[<span data-ttu-id="d0a60-120">XLL Excel中的已知问题</span><span class="sxs-lookup"><span data-stu-id="d0a60-120">Known Issues in Excel XLL Development</span></span>](known-issues-in-excel-xll-development.md)

