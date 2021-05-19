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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3f5ebc08f89651331186990d8574e3150d4f484a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410082"
---
# <a name="xlfunregister-form-1"></a><span data-ttu-id="8f3d2-104">xlfUnregister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="8f3d2-104">xlfUnregister (Form 1)</span></span>

<span data-ttu-id="8f3d2-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8f3d2-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="8f3d2-106">可以从 DLL 或 XLL 命令调用，该命令本身已由 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-106">Can be called from a DLL or XLL command that has itself been called by Microsoft Excel.</span></span> <span data-ttu-id="8f3d2-107">这相当于从 XLM 宏表Excel **UNREGISTER。**</span><span class="sxs-lookup"><span data-stu-id="8f3d2-107">This is equivalent to calling **UNREGISTER** from an Excel XLM macro sheet.</span></span> 
  
<span data-ttu-id="8f3d2-108">**xlfUnregister** 可以两种形式调用：</span><span class="sxs-lookup"><span data-stu-id="8f3d2-108">**xlfUnregister** can be called in two forms:</span></span> 
  
- <span data-ttu-id="8f3d2-109">表单 1：取消注册单个命令或函数。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-109">Form 1: Unregisters an individual command or function.</span></span>
    
- <span data-ttu-id="8f3d2-110">表单 2：卸载和停用 XLL。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-110">Form 2: Unloads and deactivates an XLL.</span></span>
    
<span data-ttu-id="8f3d2-111">此函数在窗体 1 中调用，可以减少以前使用 **xlfRegister** 或 REGISTER 注册的 DLL 函数或命令 **的使用计数**。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-111">Called in Form 1, this function reduces the use count of a DLL function or command that was previously registered using **xlfRegister** or **REGISTER**.</span></span> <span data-ttu-id="8f3d2-112">如果使用率计数已为零，则此函数不起作用。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-112">If the usage count is already zero, this function has no effect.</span></span> <span data-ttu-id="8f3d2-113">当 DLL 中所有函数的使用计数达到零时，DLL 从内存中卸载。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-113">When the use count of all the functions in a DLL reaches zero, the DLL is unloaded from memory.</span></span>
  
<span data-ttu-id="8f3d2-114">**xlfRegister** (Form 1) 还定义了一个隐藏名称，该名称是函数 text 参数  _pxFunctionText_，计算结果为函数或命令的注册 ID。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-114">**xlfRegister** (Form 1) also defines a hidden name which is the function text argument,  _pxFunctionText_, and which evaluates to the function or command's registration ID.</span></span> <span data-ttu-id="8f3d2-115">在注销函数时，应该使用 **xlfSetName** 删除此名称，以便函数向导不再列出该函数名称。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-115">When unregistering the function, this name should be deleted using **xlfSetName** so that the function name is no longer listed by the Function Wizard.</span></span> <span data-ttu-id="8f3d2-116">有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-116">For more information, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
```cs
Excel4(xlfUnregister, LPXLOPER pxRes, 1, LPXLOPER pxRegisterId);
```

## <a name="parameters"></a><span data-ttu-id="8f3d2-117">参数</span><span class="sxs-lookup"><span data-stu-id="8f3d2-117">Parameters</span></span>

<span data-ttu-id="8f3d2-118">_pxRegisterId_ (**xltypeNum**) </span><span class="sxs-lookup"><span data-stu-id="8f3d2-118">_pxRegisterId_ (**xltypeNum**)</span></span>
  
<span data-ttu-id="8f3d2-119">要注销的函数的注册 ID。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-119">The registration ID of the function to be unregistered.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8f3d2-120">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="8f3d2-120">Property value/Return value</span></span>

<span data-ttu-id="8f3d2-121">如果成功，则返回 **xltypeBool** (TRUE，) 返回 FALSE。 </span><span class="sxs-lookup"><span data-stu-id="8f3d2-121">If successful, returns **TRUE** (**xltypeBool**), otherwise it returns FALSE.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8f3d2-122">备注</span><span class="sxs-lookup"><span data-stu-id="8f3d2-122">Remarks</span></span>

<span data-ttu-id="8f3d2-123">函数的注册 ID 由 **xlfRegister** 在首次注册函数时返回。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-123">The registration ID of the function is returned by **xlfRegister** when the function is first registered.</span></span> <span data-ttu-id="8f3d2-124">它还可以通过调用 [xlfRegisterId](xlfregisterid.md) 函数或 [xlfEvaluate](xlfevaluate.md)函数获取。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-124">It can also be obtained by calling the [xlfRegisterId function](xlfregisterid.md) or the [xlfEvaluate function](xlfevaluate.md).</span></span> <span data-ttu-id="8f3d2-125">请注意，如果尚未注册函数，xlfRegisterId 将尝试注册函数。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-125">Note that xlfRegisterId tries to register the function if it has not already been registered.</span></span> <span data-ttu-id="8f3d2-126">因此，如果仅尝试获取 ID 以便可以注销 函数，最好将注册的名称传递到 **xlfEvaluate** 来获取它。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-126">For this reason, if you are only trying to get the ID so that you can unregister the function, it is better to obtain it by passing the registered name to **xlfEvaluate**.</span></span> <span data-ttu-id="8f3d2-127">如果函数尚未注册 **，xlfEvaluate** 将失败，#NAME？error。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-127">If the function has not been registered, **xlfEvaluate** fails with a #NAME? error.</span></span> 
  
## <a name="example"></a><span data-ttu-id="8f3d2-128">示例</span><span class="sxs-lookup"><span data-stu-id="8f3d2-128">Example</span></span>

<span data-ttu-id="8f3d2-129">请参阅 中的 **fExit 函数** 代码  `\SAMPLES\GENERIC\GENERIC.C` 。</span><span class="sxs-lookup"><span data-stu-id="8f3d2-129">See the code for the **fExit** function in  `\SAMPLES\GENERIC\GENERIC.C`.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="8f3d2-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f3d2-130">See also</span></span>

- [<span data-ttu-id="8f3d2-131">xlfRegister（窗体 1）</span><span class="sxs-lookup"><span data-stu-id="8f3d2-131">xlfRegister (Form 1)</span></span>](xlfregister-form-1.md)
- [<span data-ttu-id="8f3d2-132">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="8f3d2-132">xlfRegisterId</span></span>](xlfregisterid.md)
- [<span data-ttu-id="8f3d2-133">xlfUnregister（窗体 2）</span><span class="sxs-lookup"><span data-stu-id="8f3d2-133">xlfUnregister (Form 2)</span></span>](xlfunregister-form-2.md)
- [<span data-ttu-id="8f3d2-134">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="8f3d2-134">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

