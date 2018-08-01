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
ms.openlocfilehash: 6077027a27c054c5a5e65a751373c41a87cb3836
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773850"
---
# <a name="xlfunregister-form-1"></a><span data-ttu-id="807b5-104">xlfUnregister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="807b5-104">xlfUnregister (Form 1)</span></span>

<span data-ttu-id="807b5-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="807b5-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="807b5-106">可从 DLL 或 XLL 命令的本身已调用由 Microsoft Excel 进行调用。</span><span class="sxs-lookup"><span data-stu-id="807b5-106">Can be called from a DLL or XLL command that has itself been called by Microsoft Excel.</span></span> <span data-ttu-id="807b5-107">这是等效于从 Excel XLM 宏工作表调用**注销**。</span><span class="sxs-lookup"><span data-stu-id="807b5-107">This is equivalent to calling **UNREGISTER** from an Excel XLM macro sheet.</span></span> 
  
<span data-ttu-id="807b5-108">可在两个窗体中调用**xlfUnregister** :</span><span class="sxs-lookup"><span data-stu-id="807b5-108">**xlfUnregister** can be called in two forms:</span></span> 
  
- <span data-ttu-id="807b5-109">窗体 1： 取消注册的单个命令或函数。</span><span class="sxs-lookup"><span data-stu-id="807b5-109">Form 1: Unregisters an individual command or function.</span></span>
    
- <span data-ttu-id="807b5-110">窗体 2： 卸载并停用 XLL。</span><span class="sxs-lookup"><span data-stu-id="807b5-110">Form 2: Unloads and deactivates an XLL.</span></span>
    
<span data-ttu-id="807b5-111">此函数调用窗体 1 中，减少了 DLL 函数或使用**xlfRegister**或**注册**以前注册的命令使用的计数。</span><span class="sxs-lookup"><span data-stu-id="807b5-111">Called in Form 1, this function reduces the use count of a DLL function or command that was previously registered using **xlfRegister** or **REGISTER**.</span></span> <span data-ttu-id="807b5-112">如果使用次数已为零，则此函数无效。</span><span class="sxs-lookup"><span data-stu-id="807b5-112">If the usage count is already zero, this function has no effect.</span></span> <span data-ttu-id="807b5-113">当使用数目 DLL 中的所有函数为零时，DLL 是从内存中卸载。</span><span class="sxs-lookup"><span data-stu-id="807b5-113">When the use count of all the functions in a DLL reaches zero, the DLL is unloaded from memory.</span></span>
  
<span data-ttu-id="807b5-114">**xlfRegister**（窗体 1） 还定义隐藏的名称即函数文本参数， _pxFunctionText_，并对其进行计算函数或命令的注册 id。</span><span class="sxs-lookup"><span data-stu-id="807b5-114">**xlfRegister** (Form 1) also defines a hidden name which is the function text argument,  _pxFunctionText_, and which evaluates to the function or command's registration ID.</span></span> <span data-ttu-id="807b5-115">时注销函数，应使用**xlfSetName**以便函数名称不再列出由函数向导中删除此名称。</span><span class="sxs-lookup"><span data-stu-id="807b5-115">When unregistering the function, this name should be deleted using **xlfSetName** so that the function name is no longer listed by the Function Wizard.</span></span> <span data-ttu-id="807b5-116">有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="807b5-116">For more information, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
```cs
Excel4(xlfUnregister, LPXLOPER pxRes, 1, LPXLOPER pxRegisterId);
```

## <a name="parameters"></a><span data-ttu-id="807b5-117">参数</span><span class="sxs-lookup"><span data-stu-id="807b5-117">Parameters</span></span>

<span data-ttu-id="807b5-118">_pxRegisterId_(**xltypeNum**)</span><span class="sxs-lookup"><span data-stu-id="807b5-118">_pxRegisterId_ (**xltypeNum**)</span></span>
  
<span data-ttu-id="807b5-119">要取消注册函数注册 ID。</span><span class="sxs-lookup"><span data-stu-id="807b5-119">The registration ID of the function to be unregistered.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="807b5-120">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="807b5-120">Property value/Return value</span></span>

<span data-ttu-id="807b5-121">如果成功，则返回**TRUE** (**xltypeBool**)，否则为将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="807b5-121">If successful, returns **TRUE** (**xltypeBool**), otherwise it returns FALSE.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="807b5-122">说明</span><span class="sxs-lookup"><span data-stu-id="807b5-122">Remarks</span></span>

<span data-ttu-id="807b5-123">注册时的功能是第一个 ID 的函数将返回的**xlfRegister**注册。</span><span class="sxs-lookup"><span data-stu-id="807b5-123">The registration ID of the function is returned by **xlfRegister** when the function is first registered.</span></span> <span data-ttu-id="807b5-124">也可以获得通过调用[xlfRegisterId 函数](xlfregisterid.md)或[xlfEvaluate 函数](xlfevaluate.md)。</span><span class="sxs-lookup"><span data-stu-id="807b5-124">It can also be obtained by calling the [xlfRegisterId function](xlfregisterid.md) or the [xlfEvaluate function](xlfevaluate.md).</span></span> <span data-ttu-id="807b5-125">请注意该 xlfRegisterId 尝试注册功能，如果尚未注册。</span><span class="sxs-lookup"><span data-stu-id="807b5-125">Note that xlfRegisterId tries to register the function if it has not already been registered.</span></span> <span data-ttu-id="807b5-126">因此，如果只想要获取的 ID，以便可以取消注册函数，则最好获取通过将已注册的名称传递给**xlfEvaluate**。</span><span class="sxs-lookup"><span data-stu-id="807b5-126">For this reason, if you are only trying to get the ID so that you can unregister the function, it is better to obtain it by passing the registered name to **xlfEvaluate**.</span></span> <span data-ttu-id="807b5-127">如果尚未注册该函数， **xlfEvaluate**将失败并 #NAME？错误。</span><span class="sxs-lookup"><span data-stu-id="807b5-127">If the function has not been registered, **xlfEvaluate** fails with a #NAME? error.</span></span> 
  
## <a name="example"></a><span data-ttu-id="807b5-128">示例</span><span class="sxs-lookup"><span data-stu-id="807b5-128">Example</span></span>

<span data-ttu-id="807b5-129">请参阅**fExit**函数中的代码`\SAMPLES\GENERIC\GENERIC.C`。</span><span class="sxs-lookup"><span data-stu-id="807b5-129">See the code for the **fExit** function in  `\SAMPLES\GENERIC\GENERIC.C`.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="807b5-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="807b5-130">See also</span></span>

- [<span data-ttu-id="807b5-131">xlfRegister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="807b5-131">xlfRegister (Form 1)</span></span>](xlfregister-form-1.md)
- [<span data-ttu-id="807b5-132">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="807b5-132">xlfRegisterId</span></span>](xlfregisterid.md)
- [<span data-ttu-id="807b5-133">xlfUnregister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="807b5-133">xlfUnregister (Form 2)</span></span>](xlfunregister-form-2.md)
- [<span data-ttu-id="807b5-134">基本的有用 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="807b5-134">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

