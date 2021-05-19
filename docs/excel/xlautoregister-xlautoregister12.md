---
title: xlAutoRegister/xlAutoRegister12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoRegister
keywords:
- xlautoregister 函数 [excel 2007]
localization_priority: Normal
ms.assetid: aa4673cf-8e97-4678-b8d4-6a74426334f9
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f043558f3f642001e9ba11ee5b18a2721c3dddfb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421163"
---
# <a name="xlautoregisterxlautoregister12"></a><span data-ttu-id="d347a-104">xlAutoRegister/xlAutoRegister12</span><span class="sxs-lookup"><span data-stu-id="d347a-104">xlAutoRegister/xlAutoRegister12</span></span>

 <span data-ttu-id="d347a-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d347a-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d347a-106">Excel调用 XLM 函数 **REGISTER** 或 C API 等效 [xlfRegister](xlfregister-form-1.md)函数时调用 [xlAutoRegister](xlautoregister-xlautoregister12.md)函数，并且缺少函数的返回和参数类型。</span><span class="sxs-lookup"><span data-stu-id="d347a-106">Excel calls the [xlAutoRegister function](xlautoregister-xlautoregister12.md) whenever a call has been made to the XLM function **REGISTER**, or the C API equivalent [xlfRegister function](xlfregister-form-1.md), with the return and argument types of the function being registered missing.</span></span> <span data-ttu-id="d347a-107">它允许 XLL 搜索其导出函数和命令的内部列表，以使用参数注册函数并返回指定的类型。</span><span class="sxs-lookup"><span data-stu-id="d347a-107">It allows the XLL to search its internal lists of exported functions and commands to register the function with the argument and return types specified.</span></span>
  
<span data-ttu-id="d347a-108">从 2007 Excel，Excel调用 **xlAutoRegister12** 函数，如果 XLL 导出 **xlAutoRegister** 函数，则优先调用该函数。</span><span class="sxs-lookup"><span data-stu-id="d347a-108">Starting in Excel 2007, Excel calls the **xlAutoRegister12** function in preference to the **xlAutoRegister** function if it is exported by the XLL.</span></span> 
  
<span data-ttu-id="d347a-109">Excel不需要 XLL 来实现和导出其中任一函数。</span><span class="sxs-lookup"><span data-stu-id="d347a-109">Excel does not require an XLL to implement and export either of these functions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d347a-110">如果 **xlAutoRegister** /  **xlAutoRegister12** 尝试注册函数而不提供参数和返回类型，将发生递归调用循环，该循环最终会溢出调用堆栈，并Excel。</span><span class="sxs-lookup"><span data-stu-id="d347a-110">If **xlAutoRegister**/ **xlAutoRegister12** tries to register the function without supplying the argument and return types, a recursive calling loop occurs which eventually overflows the call stack and crashes Excel.</span></span> 
  
```cs
LPXLOPER12 WINAPI xlAutoRegister12(LPXLOPER12 pxName);
LPXLOPER WINAPI xlAutoRegister(LPXLOPER pxName);
```

## <a name="parameters"></a><span data-ttu-id="d347a-111">参数</span><span class="sxs-lookup"><span data-stu-id="d347a-111">Parameters</span></span>

 <span data-ttu-id="d347a-112">_pxName_ (**xltypeStr**) </span><span class="sxs-lookup"><span data-stu-id="d347a-112">_pxName_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="d347a-113">正在注册的 XLL 函数的名称。</span><span class="sxs-lookup"><span data-stu-id="d347a-113">The name of the XLL function that is being registered.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d347a-114">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="d347a-114">Property value/Return value</span></span>

<span data-ttu-id="d347a-115">函数应返回尝试使用 **xlfRegister** 函数注册 XLL 函数 _pxName_ 的尝试结果。</span><span class="sxs-lookup"><span data-stu-id="d347a-115">The function should return the result of the attempt to register the XLL function  _pxName_ using the **xlfRegister** function.</span></span> <span data-ttu-id="d347a-116">如果指定的函数不是 XLL 的导出函数之一，则它应返回 **#VALUE！**</span><span class="sxs-lookup"><span data-stu-id="d347a-116">If the specified function is not one of the XLL's exports, it should return the **#VALUE!**</span></span> <span data-ttu-id="d347a-117">error 或 **NULL，Excel** 将在 **#VALUE！ 解释。**</span><span class="sxs-lookup"><span data-stu-id="d347a-117">error, or **NULL** which Excel will interpret at **#VALUE!**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d347a-118">备注</span><span class="sxs-lookup"><span data-stu-id="d347a-118">Remarks</span></span>

<span data-ttu-id="d347a-119">**xlAutoRegister** 的实现应执行不区分大小写的搜索，搜索 XLL 导出的函数和命令的内部列表，以查找传入名称的匹配项。</span><span class="sxs-lookup"><span data-stu-id="d347a-119">Your implementation of **xlAutoRegister** should perform a case-insensitive search through your XLL's internal lists of the functions and commands it exports looking for a match with the passed-in name.</span></span> <span data-ttu-id="d347a-120">如果找到函数或命令 **，xlAutoRegister** 应尝试使用 **xlfRegister** 函数进行注册，以确保提供用于通知 Excel 函数的返回和参数类型的字符串，以及有关该函数的其他任何所需信息。</span><span class="sxs-lookup"><span data-stu-id="d347a-120">If the function or command is found, **xlAutoRegister** should attempt to register it, using the **xlfRegister** function, making sure to provide the string that tells Excel the return and argument types of the function, as well as any other required information about the function.</span></span> <span data-ttu-id="d347a-121">然后，它应返回Excel **调用 xlfRegister 返回的任何** 结果。</span><span class="sxs-lookup"><span data-stu-id="d347a-121">It should then return to Excel whatever the call to **xlfRegister** returned.</span></span> <span data-ttu-id="d347a-122">如果函数注册成功 **，xlfRegister** 将返回包含函数的 Register ID 的 **xltypeNum** 值。</span><span class="sxs-lookup"><span data-stu-id="d347a-122">If the function was registered successfully, **xlfRegister** returns an **xltypeNum** value containing the Register ID of the function.</span></span> 
  
### <a name="example"></a><span data-ttu-id="d347a-123">示例</span><span class="sxs-lookup"><span data-stu-id="d347a-123">Example</span></span>

<span data-ttu-id="d347a-124">有关此  `SAMPLES\EXAMPLE\EXAMPLE.C` 函数的示例实现，请参阅 文件。</span><span class="sxs-lookup"><span data-stu-id="d347a-124">See the file  `SAMPLES\EXAMPLE\EXAMPLE.C` for an example implementation of this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d347a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d347a-125">See also</span></span>



[<span data-ttu-id="d347a-126">REGISTER</span><span class="sxs-lookup"><span data-stu-id="d347a-126">REGISTER</span></span>](xlfregister-form-1.md)
  
[<span data-ttu-id="d347a-127">UNREGISTER</span><span class="sxs-lookup"><span data-stu-id="d347a-127">UNREGISTER</span></span>](xlfunregister-form-1.md)

