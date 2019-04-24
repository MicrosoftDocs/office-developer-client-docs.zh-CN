---
title: xlfRegisterId
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfRegisterId
keywords:
- xlfregisterid 函数 [excel 2007]
localization_priority: Normal
ms.assetid: d34cf20c-a5cd-45fb-9dcb-d49eac2d99dd
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 05119226d0b6190a2c4b30846c03a59b5c3cd1d8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303876"
---
# <a name="xlfregisterid"></a><span data-ttu-id="af603-104">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="af603-104">xlfRegisterId</span></span>

<span data-ttu-id="af603-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="af603-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="af603-106">可以从已由 Microsoft Excel 调用它本身的 DLL 调用。</span><span class="sxs-lookup"><span data-stu-id="af603-106">Can be called from a DLL that has itself been called by Microsoft Excel.</span></span> <span data-ttu-id="af603-107">如果某个函数已注册, 它将返回该函数的现有 register ID, 而不 reregistering 它。</span><span class="sxs-lookup"><span data-stu-id="af603-107">If a function is already registered, it returns the existing register ID for that function without reregistering it.</span></span> <span data-ttu-id="af603-108">如果尚未注册某个函数, 它将注册它并返回生成的寄存器 ID。</span><span class="sxs-lookup"><span data-stu-id="af603-108">If a function is not yet registered, it registers it and returns the resulting register ID.</span></span>
  
```cs
Excel12(xlfRegisterId, LPXLOPER12 pxRes, 3,     LPXLOPER12 pxModuleText, LPXLOPER12 pxProcedure, LPXLOPER12 pxTypeText);
```

## <a name="parameters"></a><span data-ttu-id="af603-109">参数</span><span class="sxs-lookup"><span data-stu-id="af603-109">Parameters</span></span>

<span data-ttu-id="af603-110">_pxModuleText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="af603-110">_pxModuleText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="af603-111">包含函数的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="af603-111">The name of the DLL containing the function.</span></span>
  
<span data-ttu-id="af603-112">_pxProcedure_(**xltypeStr**或**xltypeNum**)</span><span class="sxs-lookup"><span data-stu-id="af603-112">_pxProcedure_ (**xltypeStr** or **xltypeNum**)</span></span>
  
<span data-ttu-id="af603-113">如果为字符串, 则为要调用的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="af603-113">If a string, the name of the function to call.</span></span> <span data-ttu-id="af603-114">如果为数字, 则为要调用的函数的序号导出编号。</span><span class="sxs-lookup"><span data-stu-id="af603-114">If a number, the ordinal export number of the function to call.</span></span> <span data-ttu-id="af603-115">为清楚起见, 请始终使用字符串窗体。</span><span class="sxs-lookup"><span data-stu-id="af603-115">For clarity and robustness, always use the string form.</span></span>
  
<span data-ttu-id="af603-116">_pxTypeText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="af603-116">_pxTypeText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="af603-117">一个可选字符串, 指定函数的所有参数的类型和函数的返回值的类型。</span><span class="sxs-lookup"><span data-stu-id="af603-117">An optional string specifying the types of all the arguments to the function and the type of the return value of the function.</span></span> <span data-ttu-id="af603-118">有关详细信息，请参阅“注解”部分。</span><span class="sxs-lookup"><span data-stu-id="af603-118">For more information, see the "Remarks" section.</span></span> <span data-ttu-id="af603-119">可省略定义**xlAutoRegister**的独立 DLL (XLL) 的此参数。</span><span class="sxs-lookup"><span data-stu-id="af603-119">This argument can be omitted for a stand-alone DLL (XLL) defining **xlAutoRegister**.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="af603-120">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="af603-120">Property value/Return value</span></span>

<span data-ttu-id="af603-121">返回函数的 register ID (**xltypeNum**), 该 ID 可在后续调用**xlfUnregister**时使用。</span><span class="sxs-lookup"><span data-stu-id="af603-121">Returns the register ID of the function (**xltypeNum**), which can be used in subsequent calls to **xlfUnregister**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="af603-122">注解</span><span class="sxs-lookup"><span data-stu-id="af603-122">Remarks</span></span>

<span data-ttu-id="af603-123">如果您不想要维护收银机 ID, 但稍后需要对其进行注销, 则此函数很有用。</span><span class="sxs-lookup"><span data-stu-id="af603-123">This function is useful when you do not want to worry about maintaining a register ID, but you need one later for unregistering.</span></span> <span data-ttu-id="af603-124">当要分配的函数位于 DLL 中时, 也可以将其分配给菜单、工具和按钮。</span><span class="sxs-lookup"><span data-stu-id="af603-124">It is also useful for assigning to menus, tools, and buttons when the function you want to assign is in a DLL.</span></span>
  
<span data-ttu-id="af603-125">在已向**xlfRegister**提供有效的_pxFunctionText_参数的情况下注册 DLL 或 XLL 函数时, 也可以通过将_pxFunctionText_传递给函数**xlfEvaluate**来获取其 register ID。</span><span class="sxs-lookup"><span data-stu-id="af603-125">Where a DLL or XLL function has been registered with a valid  _pxFunctionText_ argument having been supplied to **xlfRegister**, its register ID can also be obtained by passing the  _pxFunctionText_ to the function **xlfEvaluate**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="af603-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af603-126">See also</span></span>

- [<span data-ttu-id="af603-127">注册表</span><span class="sxs-lookup"><span data-stu-id="af603-127">REGISTER</span></span>](xlfregister-form-1.md)
- [<span data-ttu-id="af603-128">注销</span><span class="sxs-lookup"><span data-stu-id="af603-128">UNREGISTER</span></span>](xlfunregister-form-1.md)
- [<span data-ttu-id="af603-129">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="af603-129">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

