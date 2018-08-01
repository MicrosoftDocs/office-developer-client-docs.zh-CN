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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 14515cc262ea398a9f200c0de3a1f6b64c758b3d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773831"
---
# <a name="xldefinebinaryname"></a><span data-ttu-id="9b334-104">xlDefineBinaryName</span><span class="sxs-lookup"><span data-stu-id="9b334-104">xlDefineBinaryName</span></span>

 <span data-ttu-id="9b334-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9b334-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="9b334-106">用于分配**xltypeBigData** **XLOPER**永久存储/ **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="9b334-106">Used to allocate persistent storage for an **xltypeBigData** **XLOPER**/ **XLOPER12**.</span></span> <span data-ttu-id="9b334-107">数据定义二进制文件名称与工作簿，保存并随时都可以通过名称访问。</span><span class="sxs-lookup"><span data-stu-id="9b334-107">Data with a defined binary name is saved with the workbook, and can be accessed by name at any time.</span></span> <span data-ttu-id="9b334-108">有关详细信息，请参阅"二进制名称范围限制" [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中。</span><span class="sxs-lookup"><span data-stu-id="9b334-108">For more information, see "Binary Name Scope Limitation" in [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
```cs
Excel12(xlDefineBinaryName, 0, 2, LPXLOPER12 pxName, LPXLOPER12 pxData);
```

## <a name="parameters"></a><span data-ttu-id="9b334-109">参数</span><span class="sxs-lookup"><span data-stu-id="9b334-109">Parameters</span></span>

 <span data-ttu-id="9b334-110">_pxName_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="9b334-110">_pxName_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="9b334-111">指定的数据的名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="9b334-111">A string specifying the name of the data.</span></span> <span data-ttu-id="9b334-112">该字符串是受到相同命名为已定义的名称的限制。</span><span class="sxs-lookup"><span data-stu-id="9b334-112">The string is subject to the same naming restrictions as defined names.</span></span>
  
 <span data-ttu-id="9b334-113">_pxData_(**xltypeBigData**)</span><span class="sxs-lookup"><span data-stu-id="9b334-113">_pxData_ (**xltypeBigData**)</span></span>
  
<span data-ttu-id="9b334-114">Bigdata 结构，它指定要存储的数据。</span><span class="sxs-lookup"><span data-stu-id="9b334-114">Bigdata structure specifying the data to be stored.</span></span> <span data-ttu-id="9b334-115">当您调用此函数时， **bigdata**结构的**lpbData**成员应指向为其正在定义名称，数据和**cbData**成员应包含以字节为单位的数据的长度。</span><span class="sxs-lookup"><span data-stu-id="9b334-115">When you call this function, the **lpbData** member of the **bigdata** structure should point to the data for which the name is being defined, and the **cbData** member should contain the length of the data in bytes.</span></span> 
  
<span data-ttu-id="9b334-116">如果_pxData_参数不是指定 (**xltypeMissing**)，将删除由_pxName_指定的命名的分配。</span><span class="sxs-lookup"><span data-stu-id="9b334-116">If the  _pxData_ argument is not specified (**xltypeMissing**), the named allocation specified by  _pxName_ is deleted.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9b334-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b334-117">See also</span></span>



[<span data-ttu-id="9b334-118">xlGetBinaryName</span><span class="sxs-lookup"><span data-stu-id="9b334-118">xlGetBinaryName</span></span>](xlgetbinaryname.md)


[<span data-ttu-id="9b334-119">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="9b334-119">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[<span data-ttu-id="9b334-120">Excel XLL 开发中的已知的问题</span><span class="sxs-lookup"><span data-stu-id="9b334-120">Known Issues in Excel XLL Development</span></span>](known-issues-in-excel-xll-development.md)

