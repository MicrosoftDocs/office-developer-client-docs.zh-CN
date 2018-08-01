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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 069676957d280a0bf3b398bb23b27f0e654bc655
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773848"
---
# <a name="xlgetname"></a><span data-ttu-id="8dec2-104">xlGetName</span><span class="sxs-lookup"><span data-stu-id="8dec2-104">xlGetName</span></span>

<span data-ttu-id="8dec2-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8dec2-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="8dec2-106">字符串的形式返回的 dll 的完整路径和文件名称。</span><span class="sxs-lookup"><span data-stu-id="8dec2-106">Returns the full path and file name of the DLL in the form of a string.</span></span>
  
```cs
Excel12(xlGetName, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a><span data-ttu-id="8dec2-107">参数</span><span class="sxs-lookup"><span data-stu-id="8dec2-107">Parameters</span></span>

<span data-ttu-id="8dec2-108">此函数具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="8dec2-108">This function has no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8dec2-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="8dec2-109">Property value/Return value</span></span>

<span data-ttu-id="8dec2-110">返回路径和文件名称 (**xltypeStr**)。</span><span class="sxs-lookup"><span data-stu-id="8dec2-110">Returns the path and file name (**xltypeStr**).</span></span> 
  
## <a name="example"></a><span data-ttu-id="8dec2-111">示例</span><span class="sxs-lookup"><span data-stu-id="8dec2-111">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8dec2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8dec2-112">See also</span></span>

- [<span data-ttu-id="8dec2-113">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="8dec2-113">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

