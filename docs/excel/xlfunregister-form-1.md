---
title: xlfUnregister（窗体 1）
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfUnregister
keywords:
- xlfunregister 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 850bf65f-a151-44d6-b49f-d53ae2c83760
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3f5ebc08f89651331186990d8574e3150d4f484a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303890"
---
# <a name="xlfunregister-form-1"></a><span data-ttu-id="20538-104">xlfUnregister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="20538-104">xlfUnregister (Form 1)</span></span>

<span data-ttu-id="20538-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="20538-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="20538-106">可从 DLL 或 XLL 命令调用, 该命令本身已由 Microsoft Excel 调用。</span><span class="sxs-lookup"><span data-stu-id="20538-106">Can be called from a DLL or XLL command that has itself been called by Microsoft Excel.</span></span> <span data-ttu-id="20538-107">这相当于从 Excel XLM 宏表中调用 "**注销**"。</span><span class="sxs-lookup"><span data-stu-id="20538-107">This is equivalent to calling **UNREGISTER** from an Excel XLM macro sheet.</span></span> 
  
<span data-ttu-id="20538-108">可以在两种形式中调用**xlfUnregister** :</span><span class="sxs-lookup"><span data-stu-id="20538-108">**xlfUnregister** can be called in two forms:</span></span> 
  
- <span data-ttu-id="20538-109">表单 1: 注销单个命令或函数。</span><span class="sxs-lookup"><span data-stu-id="20538-109">Form 1: Unregisters an individual command or function.</span></span>
    
- <span data-ttu-id="20538-110">窗体 2: 卸载和停用 XLL。</span><span class="sxs-lookup"><span data-stu-id="20538-110">Form 2: Unloads and deactivates an XLL.</span></span>
    
<span data-ttu-id="20538-111">在 Form 1 中调用, 此函数可减少以前使用**xlfRegister**或**REGISTER**注册的 DLL 函数或命令的使用次数。</span><span class="sxs-lookup"><span data-stu-id="20538-111">Called in Form 1, this function reduces the use count of a DLL function or command that was previously registered using **xlfRegister** or **REGISTER**.</span></span> <span data-ttu-id="20538-112">如果使用计数已经为零, 则此函数不起作用。</span><span class="sxs-lookup"><span data-stu-id="20538-112">If the usage count is already zero, this function has no effect.</span></span> <span data-ttu-id="20538-113">当 dll 中所有函数的使用计数达到零时, dll 将从内存中卸载。</span><span class="sxs-lookup"><span data-stu-id="20538-113">When the use count of all the functions in a DLL reaches zero, the DLL is unloaded from memory.</span></span>
  
<span data-ttu-id="20538-114">**xlfRegister**(窗体 1) 还定义了一个隐藏名称, 该名称是函数文本参数_pxFunctionText_, 其计算结果为函数或命令的注册 ID。</span><span class="sxs-lookup"><span data-stu-id="20538-114">**xlfRegister** (Form 1) also defines a hidden name which is the function text argument,  _pxFunctionText_, and which evaluates to the function or command's registration ID.</span></span> <span data-ttu-id="20538-115">在注销函数时, 应使用**xlfSetName**删除此名称, 以使函数名称不再由函数向导列出。</span><span class="sxs-lookup"><span data-stu-id="20538-115">When unregistering the function, this name should be deleted using **xlfSetName** so that the function name is no longer listed by the Function Wizard.</span></span> <span data-ttu-id="20538-116">有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="20538-116">For more information, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
```cs
Excel4(xlfUnregister, LPXLOPER pxRes, 1, LPXLOPER pxRegisterId);
```

## <a name="parameters"></a><span data-ttu-id="20538-117">参数</span><span class="sxs-lookup"><span data-stu-id="20538-117">Parameters</span></span>

<span data-ttu-id="20538-118">_pxRegisterId_(**xltypeNum**)</span><span class="sxs-lookup"><span data-stu-id="20538-118">_pxRegisterId_ (**xltypeNum**)</span></span>
  
<span data-ttu-id="20538-119">要注销的函数的注册 ID。</span><span class="sxs-lookup"><span data-stu-id="20538-119">The registration ID of the function to be unregistered.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="20538-120">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="20538-120">Property value/Return value</span></span>

<span data-ttu-id="20538-121">如果成功, 则返回**TRUE** (**xltypeBool**), 否则返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="20538-121">If successful, returns **TRUE** (**xltypeBool**), otherwise it returns FALSE.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="20538-122">注解</span><span class="sxs-lookup"><span data-stu-id="20538-122">Remarks</span></span>

<span data-ttu-id="20538-123">函数的注册 ID 在首次注册函数时由**xlfRegister**返回。</span><span class="sxs-lookup"><span data-stu-id="20538-123">The registration ID of the function is returned by **xlfRegister** when the function is first registered.</span></span> <span data-ttu-id="20538-124">也可以通过调用[xlfRegisterId 函数](xlfregisterid.md)或[xlfEvaluate 函数](xlfevaluate.md)来获取它。</span><span class="sxs-lookup"><span data-stu-id="20538-124">It can also be obtained by calling the [xlfRegisterId function](xlfregisterid.md) or the [xlfEvaluate function](xlfevaluate.md).</span></span> <span data-ttu-id="20538-125">请注意, 如果函数尚未注册, xlfRegisterId 会尝试注册该函数。</span><span class="sxs-lookup"><span data-stu-id="20538-125">Note that xlfRegisterId tries to register the function if it has not already been registered.</span></span> <span data-ttu-id="20538-126">因此, 如果您仅尝试获取 ID 以便注销该函数, 则最好通过将注册名称传递给**xlfEvaluate**来获取它。</span><span class="sxs-lookup"><span data-stu-id="20538-126">For this reason, if you are only trying to get the ID so that you can unregister the function, it is better to obtain it by passing the registered name to **xlfEvaluate**.</span></span> <span data-ttu-id="20538-127">如果函数尚未注册, **xlfEvaluate**将失败并 #NAME？误差.</span><span class="sxs-lookup"><span data-stu-id="20538-127">If the function has not been registered, **xlfEvaluate** fails with a #NAME? error.</span></span> 
  
## <a name="example"></a><span data-ttu-id="20538-128">示例</span><span class="sxs-lookup"><span data-stu-id="20538-128">Example</span></span>

<span data-ttu-id="20538-129">请参阅中`\SAMPLES\GENERIC\GENERIC.C`的**fExit**函数的代码。</span><span class="sxs-lookup"><span data-stu-id="20538-129">See the code for the **fExit** function in  `\SAMPLES\GENERIC\GENERIC.C`.</span></span>
  
```cs
int WINAPI fExit(void)
{
   XLOPER12  xDLL,    // The name of this DLL //
   xFunc,             // The name of the function //
   xRegId;            // The registration ID //
   int i;
//
// This code gets the DLL name. It then uses this along with information
// from g_rgFuncs[] to obtain a REGISTER.ID() for each function. The
// register ID is then used to unregister each function. Then the code
// frees the DLL name and calls xlAutoClose.
//
   // Make xFunc a string //
   xFunc.xltype = xltypeStr;
   Excel12f(xlGetName, &xDLL, 0);
   for (i = 0; i < g_rgWorksheetFuncsRows; i++)
   {
      xFunc.val.str = (LPWSTR) (g_rgWorksheetFuncs[i][0]);
      Excel12f(xlfRegisterId,&xRegId,2,(LPXLOPER12)&xDLL,(LPXLOPER12)&xFunc);
      Excel12f(xlfUnregister, 0, 1, (LPXLOPER12) &xRegId);
   }
   for (i = 0; i < g_rgCommandFuncsRows; i++)
   {
      xFunc.val.str = (LPWSTR) (g_rgCommandFuncs[i][0]);
      Excel12f(xlfRegisterId,&xRegId,2,(LPXLOPER12)&xDLL,(LPXLOPER12)&xFunc);
      Excel12f(xlfUnregister, 0, 1, (LPXLOPER12) &xRegId);
   }
   Excel12f(xlFree, 0, 1,  (LPXLOPER12) &xDLL);
   return xlAutoClose();
}
```

## <a name="see-also"></a><span data-ttu-id="20538-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20538-130">See also</span></span>

- [<span data-ttu-id="20538-131">xlfRegister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="20538-131">xlfRegister (Form 1)</span></span>](xlfregister-form-1.md)
- [<span data-ttu-id="20538-132">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="20538-132">xlfRegisterId</span></span>](xlfregisterid.md)
- [<span data-ttu-id="20538-133">xlfUnregister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="20538-133">xlfUnregister (Form 2)</span></span>](xlfunregister-form-2.md)
- [<span data-ttu-id="20538-134">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="20538-134">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

