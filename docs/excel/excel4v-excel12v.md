---
title: Excel4v/Excel12v
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Excel12v
- Excel4v
keywords:
- excel12v 函数 [excel 2007，] Excel4v 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: e3e96b98-c5a7-4625-95b6-a1e2d09c6d3d
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 7ffa0bc3ae6222af1ecd7f65de66d026ea178c87
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773751"
---
# <a name="excel4vexcel12v"></a><span data-ttu-id="8ce1d-104">Excel4v/Excel12v</span><span class="sxs-lookup"><span data-stu-id="8ce1d-104">Excel4v/Excel12v</span></span>

 <span data-ttu-id="8ce1d-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8ce1d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="8ce1d-106">内部 Microsoft Excel 工作表函数、 宏工作表函数或命令或仅 XLL 特殊函数或命令，从调用 DLL，XLL 或代码资源中。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-106">Calls an internal Microsoft Excel worksheet function, macro sheet function or command, or XLL-only special function or command, from within a DLL, XLL, or code resource.</span></span>
  
<span data-ttu-id="8ce1d-107">所有的最新版本的 Excel 支持**Excel4v**。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-107">All recent versions of Excel support **Excel4v**.</span></span> <span data-ttu-id="8ce1d-108">从 Excel 2007 开始，支持**Excel12v** 。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-108">Starting in Excel 2007, **Excel12v** is supported.</span></span> 
  
<span data-ttu-id="8ce1d-109">仅当 Excel 已传递给 DLL 或 XLL 的控件时，可调用这些函数。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-109">These functions can be called only when Excel has passed control to the DLL or XLL.</span></span> <span data-ttu-id="8ce1d-110">他们也称为 Excel 过后控件间接通过调用 Visual Basic for Applications (VBA)。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-110">They can also be called when Excel has passed control indirectly via a call to Visual Basic for Applications (VBA).</span></span> <span data-ttu-id="8ce1d-111">他们不能在其他任何时间调用。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-111">They cannot be called at any other time.</span></span> <span data-ttu-id="8ce1d-112">例如，他们不能为 DllMain 函数或其他时间操作系统时呼叫 dll 文件，或从由 DLL 中创建的线程在呼叫过程中调用。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-112">For example, they cannot be called during calls to the DllMain function or other times when the operating system has called the DLL, or from a thread created by the DLL.</span></span> 
  
<span data-ttu-id="8ce1d-113">[Excel4 和 Excel12](excel4-excel12.md)函数接受及其参数为堆栈上, 长度可变列表，而**Excel4v**和**Excel12v**函数接受其参数作为数组。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-113">The [Excel4 and Excel12](excel4-excel12.md) functions accept their arguments as a variable length list on the stack, whereas the **Excel4v** and **Excel12v** functions accept their arguments as an array.</span></span> <span data-ttu-id="8ce1d-114">在所有其他方面， **Excel4** **Excel4v**，相同的行为和**Excel12**行为与**Excel12v**相同。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-114">In all other respects, **Excel4** behaves the same as **Excel4v**, and **Excel12** behaves the same as **Excel12v**.</span></span>
  
```cs
int _cdecl Excel4v(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER rgx[]);
int _cdecl Excel12v(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 rgx[]);
```

## <a name="parameters"></a><span data-ttu-id="8ce1d-115">参数</span><span class="sxs-lookup"><span data-stu-id="8ce1d-115">Parameters</span></span>

 <span data-ttu-id="8ce1d-116">_iFunction_(**int**)</span><span class="sxs-lookup"><span data-stu-id="8ce1d-116">_iFunction_ (**int**)</span></span>
  
<span data-ttu-id="8ce1d-117">一个数字，指示命令、 函数或您要呼叫的特殊函数。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-117">A number that indicates the command, function, or special function you want to call.</span></span> <span data-ttu-id="8ce1d-118">有效_iFunction_值的列表，请参阅下的备注部分。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-118">For a list of valid  _iFunction_ values, see the following Remarks section.</span></span> 
  
 <span data-ttu-id="8ce1d-119">_pxRes_（**LPXLOPER**或**LPXLOPER12**）</span><span class="sxs-lookup"><span data-stu-id="8ce1d-119">_pxRes_ (**LPXLOPER** or **LPXLOPER12**)</span></span>
  
<span data-ttu-id="8ce1d-120">一个指向 （对于**Excel4v**) **XLOPER**或**XLOPER12** （对于**Excel12v**) 将保存计算函数的结果。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-120">A pointer to an **XLOPER** (in the case of **Excel4v**) or an **XLOPER12** (in the case of **Excel12v**) that will hold the result of the evaluated function.</span></span>
  
 <span data-ttu-id="8ce1d-121">_iCount_(**int**)</span><span class="sxs-lookup"><span data-stu-id="8ce1d-121">_iCount_ (**int**)</span></span>
  
<span data-ttu-id="8ce1d-122">将传递给函数的后续参数的数目。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-122">The number of subsequent arguments that will be passed to the function.</span></span> <span data-ttu-id="8ce1d-123">Excel 2003 最版本中可以是介于 0 到 30 任何号码。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-123">In versions of Excel up to 2003 this can be any number from 0 through 30.</span></span> <span data-ttu-id="8ce1d-124">从 Excel 2007 开始，这可以是任何介于 0 到 255。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-124">Starting in Excel 2007, this can be any number from 0 through 255.</span></span>
  
 <span data-ttu-id="8ce1d-125">_rgx_（**LPXLOPER []** 或**LPXLOPER12 []**）</span><span class="sxs-lookup"><span data-stu-id="8ce1d-125">_rgx_ (**LPXLOPER []** or **LPXLOPER12 []**)</span></span>
  
<span data-ttu-id="8ce1d-126">一个数组，包含对函数的参数。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-126">An array that contains the arguments to the function.</span></span> <span data-ttu-id="8ce1d-127">该数组中的所有参数都必须为**XLOPER**或**XLOPER12**值的指针。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-127">All arguments in the array must be pointers to **XLOPER** or **XLOPER12** values.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="8ce1d-128">返回值</span><span class="sxs-lookup"><span data-stu-id="8ce1d-128">Return value</span></span>

<span data-ttu-id="8ce1d-129">这些函数返回**Excel4**和**Excel12**相同的值。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-129">These functions return the same values as **Excel4** and **Excel12**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8ce1d-130">备注</span><span class="sxs-lookup"><span data-stu-id="8ce1d-130">Remarks</span></span>

<span data-ttu-id="8ce1d-131">其中的参数传递给运算符数目为变量，这些函数很有用。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-131">These functions are useful where the number of arguments passed to the operator is variable.</span></span> <span data-ttu-id="8ce1d-132">例如， **Excel4v**和**Excel12v**很有用时使用其中的总参数数目取决于所要所注册的函数的参数数目[xlfRegister](xlfregister-form-1.md)注册函数。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-132">For example, **Excel4v** and **Excel12v** are useful when you register functions by using [xlfRegister](xlfregister-form-1.md) where the number of total arguments depends on the number of arguments taken by the function being registered.</span></span> <span data-ttu-id="8ce1d-133">**Excel4v**和**Excel12v**也是有用时**Excel4**或**Excel12**编写一个包装函数。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-133">**Excel4v** and **Excel12v** are also useful when you write a wrapper function for **Excel4** or **Excel12**.</span></span> <span data-ttu-id="8ce1d-134">在这些情况下，您需要转换变量参数列表中，通常会提供给变量的大小以回调到 Excel 使用**Excel4v**或**Excel12v**的单个数组参数为**Excel4**或**Excel12**，如。</span><span class="sxs-lookup"><span data-stu-id="8ce1d-134">In these cases, you need to convert a variable argument list, as would normally be supplied to **Excel4** or **Excel12**, to a single array argument of variable size to call back into Excel by using **Excel4v** or **Excel12v**.</span></span>
  
### <a name="example"></a><span data-ttu-id="8ce1d-135">示例</span><span class="sxs-lookup"><span data-stu-id="8ce1d-135">Example</span></span>

<span data-ttu-id="8ce1d-136">代码示例，请参阅 Excel 2010 XLL SDK 安装 SDK 的以下位置中的**Excel**和**Excel12f**函数的代码：</span><span class="sxs-lookup"><span data-stu-id="8ce1d-136">For code examples, see the code for the **Excel** and **Excel12f** functions in the Excel 2010 XLL SDK, at the following location where you installed the SDK:</span></span> 
  
<span data-ttu-id="8ce1d-137">Samples\Framewrk\Framewrk.c</span><span class="sxs-lookup"><span data-stu-id="8ce1d-137">Samples\Framewrk\Framewrk.c</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8ce1d-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ce1d-138">See also</span></span>



[<span data-ttu-id="8ce1d-139">Excel4/Excel12</span><span class="sxs-lookup"><span data-stu-id="8ce1d-139">Excel4/Excel12</span></span>](excel4-excel12.md)

