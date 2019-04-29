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
# <a name="xlautoregisterxlautoregister12"></a><span data-ttu-id="b5711-104">xlAutoRegister/xlAutoRegister12</span><span class="sxs-lookup"><span data-stu-id="b5711-104">xlAutoRegister/xlAutoRegister12</span></span>

 <span data-ttu-id="b5711-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b5711-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="b5711-106">每当对 XLM 函数**REGISTER**或 C API 等效的[xlfRegister 函数](xlfregister-form-1.md)进行了调用时, Excel 将调用[xlAutoRegister 函数](xlautoregister-xlautoregister12.md), 其中包含要注册的函数的返回和参数类型。</span><span class="sxs-lookup"><span data-stu-id="b5711-106">Excel calls the [xlAutoRegister function](xlautoregister-xlautoregister12.md) whenever a call has been made to the XLM function **REGISTER**, or the C API equivalent [xlfRegister function](xlfregister-form-1.md), with the return and argument types of the function being registered missing.</span></span> <span data-ttu-id="b5711-107">它允许 XLL 搜索其导出函数和命令的内部列表, 以使用指定的参数和返回类型注册函数。</span><span class="sxs-lookup"><span data-stu-id="b5711-107">It allows the XLL to search its internal lists of exported functions and commands to register the function with the argument and return types specified.</span></span>
  
<span data-ttu-id="b5711-108">从 excel 2007 开始, 如果 XLL 导出了**xlAutoRegister**函数, excel 会在首选项中调用**xlAutoRegister12**函数。</span><span class="sxs-lookup"><span data-stu-id="b5711-108">Starting in Excel 2007, Excel calls the **xlAutoRegister12** function in preference to the **xlAutoRegister** function if it is exported by the XLL.</span></span> 
  
<span data-ttu-id="b5711-109">Excel 不需要 XLL 即可实现和导出这两个函数中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="b5711-109">Excel does not require an XLL to implement and export either of these functions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5711-110">如果**xlAutoRegister**/ **xlAutoRegister12**尝试在不提供参数和返回类型的情况下注册函数, 则会发生递归调用循环, 该循环最终会溢出调用堆栈并导致 Excel 崩溃。</span><span class="sxs-lookup"><span data-stu-id="b5711-110">If **xlAutoRegister**/ **xlAutoRegister12** tries to register the function without supplying the argument and return types, a recursive calling loop occurs which eventually overflows the call stack and crashes Excel.</span></span> 
  
```cs
LPXLOPER12 WINAPI xlAutoRegister12(LPXLOPER12 pxName);
LPXLOPER WINAPI xlAutoRegister(LPXLOPER pxName);
```

## <a name="parameters"></a><span data-ttu-id="b5711-111">参数</span><span class="sxs-lookup"><span data-stu-id="b5711-111">Parameters</span></span>

 <span data-ttu-id="b5711-112">_pxName_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="b5711-112">_pxName_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="b5711-113">正在注册的 XLL 函数的名称。</span><span class="sxs-lookup"><span data-stu-id="b5711-113">The name of the XLL function that is being registered.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b5711-114">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="b5711-114">Property value/Return value</span></span>

<span data-ttu-id="b5711-115">函数应返回尝试使用**xlfRegister**函数注册 XLL 函数_pxName_的结果。</span><span class="sxs-lookup"><span data-stu-id="b5711-115">The function should return the result of the attempt to register the XLL function  _pxName_ using the **xlfRegister** function.</span></span> <span data-ttu-id="b5711-116">如果指定的函数不是 XLL 的导出之一, 它应返回 **#VALUE!**</span><span class="sxs-lookup"><span data-stu-id="b5711-116">If the specified function is not one of the XLL's exports, it should return the **#VALUE!**</span></span> <span data-ttu-id="b5711-117">错误或**NULL** , Excel 会将其解释 **#VALUE!**。</span><span class="sxs-lookup"><span data-stu-id="b5711-117">error, or **NULL** which Excel will interpret at **#VALUE!**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b5711-118">说明</span><span class="sxs-lookup"><span data-stu-id="b5711-118">Remarks</span></span>

<span data-ttu-id="b5711-119">您的**xlAutoRegister**实现应通过您在 XLL 的函数和命令导出的函数和命令的内部列表中执行不区分大小写的搜索, 以查找与传入的名称相匹配的函数和命令。</span><span class="sxs-lookup"><span data-stu-id="b5711-119">Your implementation of **xlAutoRegister** should perform a case-insensitive search through your XLL's internal lists of the functions and commands it exports looking for a match with the passed-in name.</span></span> <span data-ttu-id="b5711-120">如果找到了函数或命令, **xlAutoRegister**应尝试使用**xlfRegister**函数注册它, 以确保提供一个字符串, 该字符串告诉 Excel 函数的返回类型和参数类型, 以及任何其他必需的有关函数的信息。</span><span class="sxs-lookup"><span data-stu-id="b5711-120">If the function or command is found, **xlAutoRegister** should attempt to register it, using the **xlfRegister** function, making sure to provide the string that tells Excel the return and argument types of the function, as well as any other required information about the function.</span></span> <span data-ttu-id="b5711-121">然后, 它应返回到 Excel 调用**xlfRegister**返回的任何内容。</span><span class="sxs-lookup"><span data-stu-id="b5711-121">It should then return to Excel whatever the call to **xlfRegister** returned.</span></span> <span data-ttu-id="b5711-122">如果函数已成功注册, **xlfRegister**将返回一个**xltypeNum**值, 其中包含函数的寄存器 ID。</span><span class="sxs-lookup"><span data-stu-id="b5711-122">If the function was registered successfully, **xlfRegister** returns an **xltypeNum** value containing the Register ID of the function.</span></span> 
  
### <a name="example"></a><span data-ttu-id="b5711-123">示例</span><span class="sxs-lookup"><span data-stu-id="b5711-123">Example</span></span>

<span data-ttu-id="b5711-124">有关此函数`SAMPLES\EXAMPLE\EXAMPLE.C`的示例实现, 请参阅文件。</span><span class="sxs-lookup"><span data-stu-id="b5711-124">See the file  `SAMPLES\EXAMPLE\EXAMPLE.C` for an example implementation of this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b5711-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5711-125">See also</span></span>



[<span data-ttu-id="b5711-126">注册表</span><span class="sxs-lookup"><span data-stu-id="b5711-126">REGISTER</span></span>](xlfregister-form-1.md)
  
[<span data-ttu-id="b5711-127">注销</span><span class="sxs-lookup"><span data-stu-id="b5711-127">UNREGISTER</span></span>](xlfunregister-form-1.md)

