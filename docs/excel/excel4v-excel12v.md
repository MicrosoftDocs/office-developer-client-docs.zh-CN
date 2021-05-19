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
- excel12v 函数 [excel 2007]，Excel4v 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: e3e96b98-c5a7-4625-95b6-a1e2d09c6d3d
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 11ab86a95dde2ad52840822b28ce4d74dd05d148
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414989"
---
# <a name="excel4vexcel12v"></a><span data-ttu-id="91ad3-104">Excel4v/Excel12v</span><span class="sxs-lookup"><span data-stu-id="91ad3-104">Excel4v/Excel12v</span></span>

 <span data-ttu-id="91ad3-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="91ad3-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="91ad3-106">从 DLL、Microsoft Excel或代码资源中调用内部工作表函数、宏工作表函数或命令或仅 XLL 的特殊函数或命令。</span><span class="sxs-lookup"><span data-stu-id="91ad3-106">Calls an internal Microsoft Excel worksheet function, macro sheet function or command, or XLL-only special function or command, from within a DLL, XLL, or code resource.</span></span>
  
<span data-ttu-id="91ad3-107">所有最新版本的 Excel都支持 **Excel4v。**</span><span class="sxs-lookup"><span data-stu-id="91ad3-107">All recent versions of Excel support **Excel4v**.</span></span> <span data-ttu-id="91ad3-108">从 2007 Excel开始，**支持 Excel12v。**</span><span class="sxs-lookup"><span data-stu-id="91ad3-108">Starting in Excel 2007, **Excel12v** is supported.</span></span> 
  
<span data-ttu-id="91ad3-109">只有在将控件传递给 DLL Excel XLL 时，才能调用这些函数。</span><span class="sxs-lookup"><span data-stu-id="91ad3-109">These functions can be called only when Excel has passed control to the DLL or XLL.</span></span> <span data-ttu-id="91ad3-110">当通过调用 VBA Excel间接传递控制权时，也可以Visual Basic for Applications (这些) 。</span><span class="sxs-lookup"><span data-stu-id="91ad3-110">They can also be called when Excel has passed control indirectly via a call to Visual Basic for Applications (VBA).</span></span> <span data-ttu-id="91ad3-111">无法在其他时间调用它们。</span><span class="sxs-lookup"><span data-stu-id="91ad3-111">They cannot be called at any other time.</span></span> <span data-ttu-id="91ad3-112">例如，在调用 DllMain 函数期间或操作系统调用 DLL 时的其他时间，或者从 DLL 创建的线程调用它们时，无法调用它们。</span><span class="sxs-lookup"><span data-stu-id="91ad3-112">For example, they cannot be called during calls to the DllMain function or other times when the operating system has called the DLL, or from a thread created by the DLL.</span></span> 
  
<span data-ttu-id="91ad3-113">[Excel4 和 Excel12](excel4-excel12.md)函数接受其参数作为堆栈上的可变长度列表，而 **Excel4v** 和 **Excel12v** 函数接受其参数作为数组。</span><span class="sxs-lookup"><span data-stu-id="91ad3-113">The [Excel4 and Excel12](excel4-excel12.md) functions accept their arguments as a variable length list on the stack, whereas the **Excel4v** and **Excel12v** functions accept their arguments as an array.</span></span> <span data-ttu-id="91ad3-114">在所有其他方面 **，Excel4** 的行为与 **Excel4v** 相同， **而 Excel12** 的行为与 **Excel12v 相同**。</span><span class="sxs-lookup"><span data-stu-id="91ad3-114">In all other respects, **Excel4** behaves the same as **Excel4v**, and **Excel12** behaves the same as **Excel12v**.</span></span>
  
```cs
int _cdecl Excel4v(int iFunction, LPXLOPER pxRes, int iCount, LPXLOPER rgx[]);
int _cdecl Excel12v(int iFunction, LPXLOPER12 pxRes, int iCount, LPXLOPER12 rgx[]);
```

## <a name="parameters"></a><span data-ttu-id="91ad3-115">参数</span><span class="sxs-lookup"><span data-stu-id="91ad3-115">Parameters</span></span>

 <span data-ttu-id="91ad3-116">_iFunction_ (**int)**</span><span class="sxs-lookup"><span data-stu-id="91ad3-116">_iFunction_ (**int**)</span></span>
  
<span data-ttu-id="91ad3-117">指示要调用的命令、函数或特殊函数的编号。</span><span class="sxs-lookup"><span data-stu-id="91ad3-117">A number that indicates the command, function, or special function you want to call.</span></span> <span data-ttu-id="91ad3-118">有关有效  _iFunction_ 值的列表，请参阅以下"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="91ad3-118">For a list of valid  _iFunction_ values, see the following Remarks section.</span></span> 
  
 <span data-ttu-id="91ad3-119">_pxRes_ (**LPXLOPER** 或 **LPXLOPER12**) </span><span class="sxs-lookup"><span data-stu-id="91ad3-119">_pxRes_ (**LPXLOPER** or **LPXLOPER12**)</span></span>
  
<span data-ttu-id="91ad3-120">一个指向 **XLOPER** (（对于 **Excel4v**) ）或 **XLOPER12** (（对于 **Excel12v**) 将保存计算函数的结果）。</span><span class="sxs-lookup"><span data-stu-id="91ad3-120">A pointer to an **XLOPER** (in the case of **Excel4v**) or an **XLOPER12** (in the case of **Excel12v**) that will hold the result of the evaluated function.</span></span>
  
 <span data-ttu-id="91ad3-121">_iCount_ (**int)**</span><span class="sxs-lookup"><span data-stu-id="91ad3-121">_iCount_ (**int**)</span></span>
  
<span data-ttu-id="91ad3-122">将传递给函数的后续参数的数量。</span><span class="sxs-lookup"><span data-stu-id="91ad3-122">The number of subsequent arguments that will be passed to the function.</span></span> <span data-ttu-id="91ad3-123">在 Excel 2003 版本中，它可以是 0 到 30 的任何数字。</span><span class="sxs-lookup"><span data-stu-id="91ad3-123">In versions of Excel up to 2003 this can be any number from 0 through 30.</span></span> <span data-ttu-id="91ad3-124">从 Excel 2007 开始，可以是从 0 到 255 的任何数字。</span><span class="sxs-lookup"><span data-stu-id="91ad3-124">Starting in Excel 2007, this can be any number from 0 through 255.</span></span>
  
 <span data-ttu-id="91ad3-125">_rgx_ (**LPXLOPER []** 或 **LPXLOPER12 [])**</span><span class="sxs-lookup"><span data-stu-id="91ad3-125">_rgx_ (**LPXLOPER []** or **LPXLOPER12 []**)</span></span>
  
<span data-ttu-id="91ad3-126">包含函数参数的数组。</span><span class="sxs-lookup"><span data-stu-id="91ad3-126">An array that contains the arguments to the function.</span></span> <span data-ttu-id="91ad3-127">数组中所有参数都必须是指向 **XLOPER** 或 **XLOPER12** 值的指针。</span><span class="sxs-lookup"><span data-stu-id="91ad3-127">All arguments in the array must be pointers to **XLOPER** or **XLOPER12** values.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="91ad3-128">返回值</span><span class="sxs-lookup"><span data-stu-id="91ad3-128">Return value</span></span>

<span data-ttu-id="91ad3-129">这些函数返回与 **Excel4** 和 **Excel12** 相同的值。</span><span class="sxs-lookup"><span data-stu-id="91ad3-129">These functions return the same values as **Excel4** and **Excel12**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="91ad3-130">备注</span><span class="sxs-lookup"><span data-stu-id="91ad3-130">Remarks</span></span>

<span data-ttu-id="91ad3-131">当传递给运算符的参数数目为变量时，这些函数非常有用。</span><span class="sxs-lookup"><span data-stu-id="91ad3-131">These functions are useful where the number of arguments passed to the operator is variable.</span></span> <span data-ttu-id="91ad3-132">例如，在使用 [xlfRegister](xlfregister-form-1.md)注册函数时 **，Excel4v** 和 **Excel12v** 非常有用，其中总参数数取决于注册的函数所采用参数的数量。</span><span class="sxs-lookup"><span data-stu-id="91ad3-132">For example, **Excel4v** and **Excel12v** are useful when you register functions by using [xlfRegister](xlfregister-form-1.md) where the number of total arguments depends on the number of arguments taken by the function being registered.</span></span> <span data-ttu-id="91ad3-133">**编写 Excel4** 或 **Excel12** 的包装函数时 **，Excel4v** 和 **Excel12v 也很有用**。</span><span class="sxs-lookup"><span data-stu-id="91ad3-133">**Excel4v** and **Excel12v** are also useful when you write a wrapper function for **Excel4** or **Excel12**.</span></span> <span data-ttu-id="91ad3-134">在这些情况下，您需要将变量参数列表（通常提供给 **Excel4** 或 **Excel12）** 转换为变量大小的单个数组参数，以使用 **Excel4v** 或 **Excel12v** 调用回 Excel。</span><span class="sxs-lookup"><span data-stu-id="91ad3-134">In these cases, you need to convert a variable argument list, as would normally be supplied to **Excel4** or **Excel12**, to a single array argument of variable size to call back into Excel by using **Excel4v** or **Excel12v**.</span></span>
  
### <a name="example"></a><span data-ttu-id="91ad3-135">示例</span><span class="sxs-lookup"><span data-stu-id="91ad3-135">Example</span></span>

<span data-ttu-id="91ad3-136">有关代码示例，请参阅安装 SDK的以下位置的 Excel 2010 XLL SDK 中的 Excel 和 **Excel12f** 函数的代码：</span><span class="sxs-lookup"><span data-stu-id="91ad3-136">For code examples, see the code for the **Excel** and **Excel12f** functions in the Excel 2010 XLL SDK, at the following location where you installed the SDK:</span></span> 
  
<span data-ttu-id="91ad3-137">Samples\Framewrk\Framewrk.c</span><span class="sxs-lookup"><span data-stu-id="91ad3-137">Samples\Framewrk\Framewrk.c</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91ad3-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91ad3-138">See also</span></span>



[<span data-ttu-id="91ad3-139">Excel4/Excel12</span><span class="sxs-lookup"><span data-stu-id="91ad3-139">Excel4/Excel12</span></span>](excel4-excel12.md)

