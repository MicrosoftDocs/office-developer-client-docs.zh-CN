---
title: xlUDF
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlUDF
keywords:
- xludf 函数 [excel 2007]
localization_priority: Normal
ms.assetid: b608b356-ca5c-47bb-9de8-9b7e2b3924dd
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 8f45f800ca50d2a46792e7cf5e00ac25bd099e8c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773869"
---
# <a name="xludf"></a><span data-ttu-id="5528e-104">xlUDF</span><span class="sxs-lookup"><span data-stu-id="5528e-104">xlUDF</span></span>

<span data-ttu-id="5528e-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5528e-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="5528e-106">调用用户定义函数 (UDF)。</span><span class="sxs-lookup"><span data-stu-id="5528e-106">Calls a user-defined function (UDF).</span></span> <span data-ttu-id="5528e-107">此功能允许 DLL 调用 Visual Basic for Applications (VBA) 用户定义的函数、 XLM 宏语言函数和注册其他加载项中包含的函数。</span><span class="sxs-lookup"><span data-stu-id="5528e-107">This function allows a DLL to call Visual Basic for Applications (VBA) user-defined functions, XLM macro language functions, and registered functions contained in other add-ins.</span></span>
  
```cs
Excel12(xlUDF, LPXLOPER12 pxRes, int iCount, LPXLOPER12 pxFnRef,
LPXLOPER12 pxArg1, ...);
```

## <a name="parameters"></a><span data-ttu-id="5528e-108">参数</span><span class="sxs-lookup"><span data-stu-id="5528e-108">Parameters</span></span>

<span data-ttu-id="5528e-109">_pxFnRef_（**xltypeRef**、 **xltypeSRef**、 **xltypeStr**或**xltypeNum**）</span><span class="sxs-lookup"><span data-stu-id="5528e-109">_pxFnRef_ (**xltypeRef**, **xltypeSRef**, **xltypeStr** or **xltypeNum**)</span></span>
  
<span data-ttu-id="5528e-110">要调用的函数的引用。</span><span class="sxs-lookup"><span data-stu-id="5528e-110">The reference of the function you want to call.</span></span> <span data-ttu-id="5528e-111">这可以是宏工作表单元格引用，作为字符串函数的已注册名称或注册 ID 的函数。</span><span class="sxs-lookup"><span data-stu-id="5528e-111">This can be a macro sheet cell reference, the registered name of the function as a string, or the register ID of the function.</span></span> <span data-ttu-id="5528e-112">对于 XLL 加载项函数注册使用提供的参数_pxFunctionText_ **xlfRegister**或**注册**，可以通过使用**xlfEvaluate**查找名称获得 ID。</span><span class="sxs-lookup"><span data-stu-id="5528e-112">For XLL add-in functions registered using **xlfRegister** or **REGISTER** with the argument  _pxFunctionText_ supplied, the ID can be obtained by using **xlfEvaluate** to look up the name.</span></span> 
  
<span data-ttu-id="5528e-113">_pxArg1..._</span><span class="sxs-lookup"><span data-stu-id="5528e-113">_pxArg1, ..._</span></span>
  
<span data-ttu-id="5528e-114">零个或多个用户定义函数的参数。</span><span class="sxs-lookup"><span data-stu-id="5528e-114">Zero or more arguments to the user-defined function.</span></span> <span data-ttu-id="5528e-115">时要调用此函数中版本早于 Excel 2007，可以传递的其他参数的最大数量为 29，这是 30 包括_pxFnRef_。</span><span class="sxs-lookup"><span data-stu-id="5528e-115">When you are calling this function in versions earlier than Excel 2007, the maximum number of additional arguments that can be passed is 29, which is 30 including  _pxFnRef_.</span></span> <span data-ttu-id="5528e-116">从 Excel 2007 开始，此限制增加到 254，这是 255 包括_pxFnRef_。</span><span class="sxs-lookup"><span data-stu-id="5528e-116">Starting in Excel 2007, this limit is raised to 254, which is 255 including  _pxFnRef_.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="5528e-117">返回值</span><span class="sxs-lookup"><span data-stu-id="5528e-117">Return value</span></span>

<span data-ttu-id="5528e-118">返回任何值返回的用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="5528e-118">Returns whatever value the user-defined function returned.</span></span>
  
## <a name="example"></a><span data-ttu-id="5528e-119">示例</span><span class="sxs-lookup"><span data-stu-id="5528e-119">Example</span></span>

<span data-ttu-id="5528e-120">下面的示例表 Macro1 BOOK1 中运行**TestMacro** 。XLS。</span><span class="sxs-lookup"><span data-stu-id="5528e-120">The following example runs **TestMacro** on sheet Macro1 in BOOK1.XLS.</span></span> <span data-ttu-id="5528e-121">请确保为宏名为 Macro1 工作表上。</span><span class="sxs-lookup"><span data-stu-id="5528e-121">Make sure that the macro is on a sheet named Macro1.</span></span> 
  
`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlUDFExample(void)
{       
   XLOPER12 xMacroName, xMacroRef, xRes;
   xMacroName.xltype = xltypeStr;
   xMacroName.val.str = L"\044[BOOK1.XLSX]Macro1!TestMacro";
   Excel12(xlfEvaluate, &xMacroRef, 1, (LPXLOPER12)&xMacroName);
   Excel12(xlUDF, &xRes, 1, (LPXLOPER12)&xMacroRef);
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="5528e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5528e-122">See also</span></span>

- [<span data-ttu-id="5528e-123">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="5528e-123">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

