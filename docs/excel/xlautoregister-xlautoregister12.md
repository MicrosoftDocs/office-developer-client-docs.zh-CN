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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: e6430a54b0c0ed3b6e08d3c9256cae7dcde926ab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773830"
---
# <a name="xlautoregisterxlautoregister12"></a><span data-ttu-id="e196d-104">xlAutoRegister/xlAutoRegister12</span><span class="sxs-lookup"><span data-stu-id="e196d-104">xlAutoRegister/xlAutoRegister12</span></span>

 <span data-ttu-id="e196d-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e196d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="e196d-106">每当呼叫对进行了**注册**，XLM 函数或 C API 等效[xlfRegister 函数](xlfregister-form-1.md)，要所注册的函数的返回和参数类型与丢失，Excel 将调用[xlAutoRegister 函数](xlautoregister-xlautoregister12.md)。</span><span class="sxs-lookup"><span data-stu-id="e196d-106">Excel calls the [xlAutoRegister function](xlautoregister-xlautoregister12.md) whenever a call has been made to the XLM function **REGISTER**, or the C API equivalent [xlfRegister function](xlfregister-form-1.md), with the return and argument types of the function being registered missing.</span></span> <span data-ttu-id="e196d-107">它允许 XLL 搜索其内部导出的函数和命令来注册功能使用参数并返回指定类型的列表。</span><span class="sxs-lookup"><span data-stu-id="e196d-107">It allows the XLL to search its internal lists of exported functions and commands to register the function with the argument and return types specified.</span></span>
  
<span data-ttu-id="e196d-108">从 Excel 2007 开始，Excel 调用优先于**xlAutoRegister**函数**xlAutoRegister12**函数的操作，如果它通过 XLL 导出。</span><span class="sxs-lookup"><span data-stu-id="e196d-108">Starting in Excel 2007, Excel calls the **xlAutoRegister12** function in preference to the **xlAutoRegister** function if it is exported by the XLL.</span></span> 
  
<span data-ttu-id="e196d-109">Excel 不需要 XLL 实施和导出其中任一函数。</span><span class="sxs-lookup"><span data-stu-id="e196d-109">Excel does not require an XLL to implement and export either of these functions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e196d-110">如果**xlAutoRegister**/ **xlAutoRegister12**尝试函数注册无需提供参数和返回类型、 递归调用循环发生最终溢出调用堆栈和崩溃 Excel。</span><span class="sxs-lookup"><span data-stu-id="e196d-110">If **xlAutoRegister**/ **xlAutoRegister12** tries to register the function without supplying the argument and return types, a recursive calling loop occurs which eventually overflows the call stack and crashes Excel.</span></span> 
  
```cs
LPXLOPER12 WINAPI xlAutoRegister12(LPXLOPER12 pxName);
LPXLOPER WINAPI xlAutoRegister(LPXLOPER pxName);
```

## <a name="parameters"></a><span data-ttu-id="e196d-111">参数</span><span class="sxs-lookup"><span data-stu-id="e196d-111">Parameters</span></span>

 <span data-ttu-id="e196d-112">_pxName_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="e196d-112">_pxName_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="e196d-113">正在注册 XLL 函数的名称。</span><span class="sxs-lookup"><span data-stu-id="e196d-113">The name of the XLL function that is being registered.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e196d-114">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="e196d-114">Property value/Return value</span></span>

<span data-ttu-id="e196d-115">函数应返回尝试注册 XLL 函数_pxName_使用**xlfRegister**函数的结果。</span><span class="sxs-lookup"><span data-stu-id="e196d-115">The function should return the result of the attempt to register the XLL function  _pxName_ using the **xlfRegister** function.</span></span> <span data-ttu-id="e196d-116">如果指定的函数不是 XLL 的导出之一，则应返回 **#VALUE ！**</span><span class="sxs-lookup"><span data-stu-id="e196d-116">If the specified function is not one of the XLL's exports, it should return the **#VALUE!**</span></span> <span data-ttu-id="e196d-117">错误，或**NULL** Excel 会将解释在 **#VALUE ！**。</span><span class="sxs-lookup"><span data-stu-id="e196d-117">error, or **NULL** which Excel will interpret at **#VALUE!**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e196d-118">备注</span><span class="sxs-lookup"><span data-stu-id="e196d-118">Remarks</span></span>

<span data-ttu-id="e196d-119">**XlAutoRegister**的实现应执行不区分大小写搜索通过 XLL 的内部函数和它导出查找具有传入的名称匹配的命令列表。</span><span class="sxs-lookup"><span data-stu-id="e196d-119">Your implementation of **xlAutoRegister** should perform a case-insensitive search through your XLL's internal lists of the functions and commands it exports looking for a match with the passed-in name.</span></span> <span data-ttu-id="e196d-120">如果找到函数或命令，则**xlAutoRegister**应尝试注册它，使用**xlfRegister**函数，并确保提供告诉返回和参数的函数，以及任何其他所需类型的 Excel 的字符串有关函数的信息。</span><span class="sxs-lookup"><span data-stu-id="e196d-120">If the function or command is found, **xlAutoRegister** should attempt to register it, using the **xlfRegister** function, making sure to provide the string that tells Excel the return and argument types of the function, as well as any other required information about the function.</span></span> <span data-ttu-id="e196d-121">它应将返回到 Excel 到**xlfRegister**的调用返回的任何内容。</span><span class="sxs-lookup"><span data-stu-id="e196d-121">It should then return to Excel whatever the call to **xlfRegister** returned.</span></span> <span data-ttu-id="e196d-122">如果已成功注册的函数， **xlfRegister**将返回包含的函数的注册 ID **xltypeNum**值。</span><span class="sxs-lookup"><span data-stu-id="e196d-122">If the function was registered successfully, **xlfRegister** returns an **xltypeNum** value containing the Register ID of the function.</span></span> 
  
### <a name="example"></a><span data-ttu-id="e196d-123">示例</span><span class="sxs-lookup"><span data-stu-id="e196d-123">Example</span></span>

<span data-ttu-id="e196d-124">请参阅文件`SAMPLES\EXAMPLE\EXAMPLE.C`示例实现的此函数。</span><span class="sxs-lookup"><span data-stu-id="e196d-124">See the file  `SAMPLES\EXAMPLE\EXAMPLE.C` for an example implementation of this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e196d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e196d-125">See also</span></span>



[<span data-ttu-id="e196d-126">注册</span><span class="sxs-lookup"><span data-stu-id="e196d-126">REGISTER</span></span>](xlfregister-form-1.md)
  
[<span data-ttu-id="e196d-127">注销</span><span class="sxs-lookup"><span data-stu-id="e196d-127">UNREGISTER</span></span>](xlfunregister-form-1.md)

