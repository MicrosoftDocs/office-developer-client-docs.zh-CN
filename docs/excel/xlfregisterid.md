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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 05119226d0b6190a2c4b30846c03a59b5c3cd1d8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420057"
---
# <a name="xlfregisterid"></a><span data-ttu-id="323ba-104">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="323ba-104">xlfRegisterId</span></span>

<span data-ttu-id="323ba-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="323ba-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="323ba-106">可以从已由 Microsoft Excel 调用的 DLL 中调用。</span><span class="sxs-lookup"><span data-stu-id="323ba-106">Can be called from a DLL that has itself been called by Microsoft Excel.</span></span> <span data-ttu-id="323ba-107">如果函数已经注册，它将返回该函数的现有注册 ID，而不重新注册它。</span><span class="sxs-lookup"><span data-stu-id="323ba-107">If a function is already registered, it returns the existing register ID for that function without reregistering it.</span></span> <span data-ttu-id="323ba-108">如果函数尚未注册，它将注册它并返回生成的注册 ID。</span><span class="sxs-lookup"><span data-stu-id="323ba-108">If a function is not yet registered, it registers it and returns the resulting register ID.</span></span>
  
```cs
Excel12(xlfRegisterId, LPXLOPER12 pxRes, 3,     LPXLOPER12 pxModuleText, LPXLOPER12 pxProcedure, LPXLOPER12 pxTypeText);
```

## <a name="parameters"></a><span data-ttu-id="323ba-109">参数</span><span class="sxs-lookup"><span data-stu-id="323ba-109">Parameters</span></span>

<span data-ttu-id="323ba-110">_pxModuleText_ (**xltypeStr**) </span><span class="sxs-lookup"><span data-stu-id="323ba-110">_pxModuleText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="323ba-111">包含 函数的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="323ba-111">The name of the DLL containing the function.</span></span>
  
<span data-ttu-id="323ba-112">_pxProcedure_ (**xltypeStr** 或 **xltypeNum**) </span><span class="sxs-lookup"><span data-stu-id="323ba-112">_pxProcedure_ (**xltypeStr** or **xltypeNum**)</span></span>
  
<span data-ttu-id="323ba-113">如果是字符串，则表示要调用的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="323ba-113">If a string, the name of the function to call.</span></span> <span data-ttu-id="323ba-114">如果是数字，则表示要调用的函数的序号导出号。</span><span class="sxs-lookup"><span data-stu-id="323ba-114">If a number, the ordinal export number of the function to call.</span></span> <span data-ttu-id="323ba-115">为清楚和可靠，请始终使用字符串形式。</span><span class="sxs-lookup"><span data-stu-id="323ba-115">For clarity and robustness, always use the string form.</span></span>
  
<span data-ttu-id="323ba-116">_pxTypeText_ (**xltypeStr**) </span><span class="sxs-lookup"><span data-stu-id="323ba-116">_pxTypeText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="323ba-117">一个可选字符串，用于指定函数的所有参数的类型以及函数的返回值类型。</span><span class="sxs-lookup"><span data-stu-id="323ba-117">An optional string specifying the types of all the arguments to the function and the type of the return value of the function.</span></span> <span data-ttu-id="323ba-118">有关详细信息，请参阅“注解”部分。</span><span class="sxs-lookup"><span data-stu-id="323ba-118">For more information, see the "Remarks" section.</span></span> <span data-ttu-id="323ba-119">对于定义 **xlAutoRegister** 的 XLL 独立 DLL (可以) 此参数。</span><span class="sxs-lookup"><span data-stu-id="323ba-119">This argument can be omitted for a stand-alone DLL (XLL) defining **xlAutoRegister**.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="323ba-120">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="323ba-120">Property value/Return value</span></span>

<span data-ttu-id="323ba-121">返回函数 **xltypeNum** (的注册 ID) ，该 id 可用于对 **xlfUnregister 的后续调用**。</span><span class="sxs-lookup"><span data-stu-id="323ba-121">Returns the register ID of the function (**xltypeNum**), which can be used in subsequent calls to **xlfUnregister**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="323ba-122">备注</span><span class="sxs-lookup"><span data-stu-id="323ba-122">Remarks</span></span>

<span data-ttu-id="323ba-123">如果您不想维护注册 ID，但稍后需要一个注册 ID，则此函数非常有用。</span><span class="sxs-lookup"><span data-stu-id="323ba-123">This function is useful when you do not want to worry about maintaining a register ID, but you need one later for unregistering.</span></span> <span data-ttu-id="323ba-124">当要分配的函数位于 DLL 中时，它还可用于分配给菜单、工具和按钮。</span><span class="sxs-lookup"><span data-stu-id="323ba-124">It is also useful for assigning to menus, tools, and buttons when the function you want to assign is in a DLL.</span></span>
  
<span data-ttu-id="323ba-125">如果 DLL 或 XLL 函数已使用提供给 **xlfRegister** 的有效 _pxFunctionText_ 参数进行注册，则也可通过向函数 **xlfEvaluate** 传递 _pxFunctionText_ 来获取其注册 ID。</span><span class="sxs-lookup"><span data-stu-id="323ba-125">Where a DLL or XLL function has been registered with a valid  _pxFunctionText_ argument having been supplied to **xlfRegister**, its register ID can also be obtained by passing the  _pxFunctionText_ to the function **xlfEvaluate**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="323ba-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="323ba-126">See also</span></span>

- [<span data-ttu-id="323ba-127">REGISTER</span><span class="sxs-lookup"><span data-stu-id="323ba-127">REGISTER</span></span>](xlfregister-form-1.md)
- [<span data-ttu-id="323ba-128">UNREGISTER</span><span class="sxs-lookup"><span data-stu-id="323ba-128">UNREGISTER</span></span>](xlfunregister-form-1.md)
- [<span data-ttu-id="323ba-129">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="323ba-129">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

