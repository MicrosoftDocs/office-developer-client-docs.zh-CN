---
title: xlGetName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlGetName
keywords:
- xlgetname 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 72dbebc0-7436-4771-8fbf-2b445341da65
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 350ae99baf088a36fa3e1159caa1805cdd623276
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430586"
---
# <a name="xlgetname"></a><span data-ttu-id="bfe50-104">xlGetName</span><span class="sxs-lookup"><span data-stu-id="bfe50-104">xlGetName</span></span>

<span data-ttu-id="bfe50-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bfe50-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="bfe50-106">以字符串的形式返回 DLL 的完整路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="bfe50-106">Returns the full path and file name of the DLL in the form of a string.</span></span>
  
```cs
Excel12(xlGetName, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a><span data-ttu-id="bfe50-107">参数</span><span class="sxs-lookup"><span data-stu-id="bfe50-107">Parameters</span></span>

<span data-ttu-id="bfe50-108">此函数没有参数。</span><span class="sxs-lookup"><span data-stu-id="bfe50-108">This function has no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bfe50-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="bfe50-109">Property value/Return value</span></span>

<span data-ttu-id="bfe50-110">返回路径和文件名 (**xltypeStr**)。</span><span class="sxs-lookup"><span data-stu-id="bfe50-110">Returns the path and file name (**xltypeStr**).</span></span> 
  
## <a name="example"></a><span data-ttu-id="bfe50-111">示例</span><span class="sxs-lookup"><span data-stu-id="bfe50-111">Example</span></span>

`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlGetNameExample(void)
{
    XLOPER12 xRes;
    Excel12(xlGetName, (LPXLOPER12)&xRes, 0);
    Excel12(xlcAlert, 0, 1, (LPXLOPER12)&xRes);
    Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes);
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="bfe50-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfe50-112">See also</span></span>

- [<span data-ttu-id="bfe50-113">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="bfe50-113">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

