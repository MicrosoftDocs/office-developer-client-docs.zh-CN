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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 569334847c7612b86f6ddc967f159e2ef425cbbb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430642"
---
# <a name="xludf"></a><span data-ttu-id="c6221-104">xlUDF</span><span class="sxs-lookup"><span data-stu-id="c6221-104">xlUDF</span></span>

<span data-ttu-id="c6221-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c6221-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c6221-106">使用 UDF 函数 (用户) 。</span><span class="sxs-lookup"><span data-stu-id="c6221-106">Calls a user-defined function (UDF).</span></span> <span data-ttu-id="c6221-107">此函数允许 DLL 调用 Visual Basic for Applications (VBA) 用户定义函数、XLM 宏语言函数和其他加载项中包含的已注册函数。</span><span class="sxs-lookup"><span data-stu-id="c6221-107">This function allows a DLL to call Visual Basic for Applications (VBA) user-defined functions, XLM macro language functions, and registered functions contained in other add-ins.</span></span>
  
```cs
Excel12(xlUDF, LPXLOPER12 pxRes, int iCount, LPXLOPER12 pxFnRef,
LPXLOPER12 pxArg1, ...);
```

## <a name="parameters"></a><span data-ttu-id="c6221-108">参数</span><span class="sxs-lookup"><span data-stu-id="c6221-108">Parameters</span></span>

<span data-ttu-id="c6221-109">_pxFnRef_ (xltypeRef、xltypeSRef、xltypeStr 或 **xltypeNum**)   </span><span class="sxs-lookup"><span data-stu-id="c6221-109">_pxFnRef_ (**xltypeRef**, **xltypeSRef**, **xltypeStr** or **xltypeNum**)</span></span>
  
<span data-ttu-id="c6221-110">要调用的函数的引用。</span><span class="sxs-lookup"><span data-stu-id="c6221-110">The reference of the function you want to call.</span></span> <span data-ttu-id="c6221-111">它可以是宏工作表单元格引用、字符串形式函数的注册名称或函数的注册 ID。</span><span class="sxs-lookup"><span data-stu-id="c6221-111">This can be a macro sheet cell reference, the registered name of the function as a string, or the register ID of the function.</span></span> <span data-ttu-id="c6221-112">对于使用 **xlfRegister 或** **REGISTER（** 提供的参数  _pxFunctionText）_ 注册的 XLL 加载项函数，可以通过使用 **xlfEvaluate** 查找名称来获取 ID。</span><span class="sxs-lookup"><span data-stu-id="c6221-112">For XLL add-in functions registered using **xlfRegister** or **REGISTER** with the argument  _pxFunctionText_ supplied, the ID can be obtained by using **xlfEvaluate** to look up the name.</span></span> 
  
<span data-ttu-id="c6221-113">_pxArg1， ..._</span><span class="sxs-lookup"><span data-stu-id="c6221-113">_pxArg1, ..._</span></span>
  
<span data-ttu-id="c6221-114">用户定义的函数的零个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="c6221-114">Zero or more arguments to the user-defined function.</span></span> <span data-ttu-id="c6221-115">在 Excel 2007 以前的版本中调用此函数时，可以传递的其他参数的最大数量为 29，即 30（包括 _pxFnRef）。_</span><span class="sxs-lookup"><span data-stu-id="c6221-115">When you are calling this function in versions earlier than Excel 2007, the maximum number of additional arguments that can be passed is 29, which is 30 including  _pxFnRef_.</span></span> <span data-ttu-id="c6221-116">从 2007 Excel，此限制将提升至 254，即 255（包括 _pxFnRef）。_</span><span class="sxs-lookup"><span data-stu-id="c6221-116">Starting in Excel 2007, this limit is raised to 254, which is 255 including  _pxFnRef_.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="c6221-117">返回值</span><span class="sxs-lookup"><span data-stu-id="c6221-117">Return value</span></span>

<span data-ttu-id="c6221-118">返回用户定义函数返回的任何值。</span><span class="sxs-lookup"><span data-stu-id="c6221-118">Returns whatever value the user-defined function returned.</span></span>
  
## <a name="example"></a><span data-ttu-id="c6221-119">示例</span><span class="sxs-lookup"><span data-stu-id="c6221-119">Example</span></span>

<span data-ttu-id="c6221-120">下面的示例在工作表 **Macro1** 上的 BOOK1.XLS。</span><span class="sxs-lookup"><span data-stu-id="c6221-120">The following example runs **TestMacro** on sheet Macro1 in BOOK1.XLS.</span></span> <span data-ttu-id="c6221-121">确保宏位于名为 Macro1 的工作表上。</span><span class="sxs-lookup"><span data-stu-id="c6221-121">Make sure that the macro is on a sheet named Macro1.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="c6221-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6221-122">See also</span></span>

- [<span data-ttu-id="c6221-123">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="c6221-123">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

