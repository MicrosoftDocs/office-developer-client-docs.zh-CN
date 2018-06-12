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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: cd401393b7465442cef9342b942a27456871c68b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773855"
---
# <a name="xlfregisterid"></a><span data-ttu-id="74caf-104">xlfRegisterId</span><span class="sxs-lookup"><span data-stu-id="74caf-104">xlfRegisterId</span></span>

<span data-ttu-id="74caf-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="74caf-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="74caf-106">可从本身已调用由 Microsoft Excel DLL 调用。</span><span class="sxs-lookup"><span data-stu-id="74caf-106">Can be called from a DLL that has itself been called by Microsoft Excel.</span></span> <span data-ttu-id="74caf-107">如果已注册一个函数，它将返回该函数的现有注册 ID，而不重新注册它。</span><span class="sxs-lookup"><span data-stu-id="74caf-107">If a function is already registered, it returns the existing register ID for that function without reregistering it.</span></span> <span data-ttu-id="74caf-108">如果尚未未注册一个函数，它将其注册并返回结果注册 id。</span><span class="sxs-lookup"><span data-stu-id="74caf-108">If a function is not yet registered, it registers it and returns the resulting register ID.</span></span>
  
```cs
Excel12(xlfRegisterId, LPXLOPER12 pxRes, 3,     LPXLOPER12 pxModuleText, LPXLOPER12 pxProcedure, LPXLOPER12 pxTypeText);
```

## <a name="parameters"></a><span data-ttu-id="74caf-109">参数</span><span class="sxs-lookup"><span data-stu-id="74caf-109">Parameters</span></span>

<span data-ttu-id="74caf-110">_pxModuleText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="74caf-110">_pxModuleText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="74caf-111">包含该函数的 dll 名称。</span><span class="sxs-lookup"><span data-stu-id="74caf-111">The name of the DLL containing the function.</span></span>
  
<span data-ttu-id="74caf-112">_pxProcedure_（**xltypeStr**或**xltypeNum**）</span><span class="sxs-lookup"><span data-stu-id="74caf-112">_pxProcedure_ (**xltypeStr** or **xltypeNum**)</span></span>
  
<span data-ttu-id="74caf-113">如果要调用的函数的名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="74caf-113">If a string, the name of the function to call.</span></span> <span data-ttu-id="74caf-114">如果一个号码，序号导出要调用的函数的数量。</span><span class="sxs-lookup"><span data-stu-id="74caf-114">If a number, the ordinal export number of the function to call.</span></span> <span data-ttu-id="74caf-115">为清楚起见和可靠性，始终使用字符串形式。</span><span class="sxs-lookup"><span data-stu-id="74caf-115">For clarity and robustness, always use the string form.</span></span>
  
<span data-ttu-id="74caf-116">_pxTypeText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="74caf-116">_pxTypeText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="74caf-117">可选字符串指定给函数的所有参数的类型和函数的返回值的类型。</span><span class="sxs-lookup"><span data-stu-id="74caf-117">An optional string specifying the types of all the arguments to the function and the type of the return value of the function.</span></span> <span data-ttu-id="74caf-118">有关详细信息，请参阅"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="74caf-118">For more information, see the "Remarks" section.</span></span> <span data-ttu-id="74caf-119">可以省略该参数为独立 DLL (XLL) 定义**xlAutoRegister**。</span><span class="sxs-lookup"><span data-stu-id="74caf-119">This argument can be omitted for a stand-alone DLL (XLL) defining **xlAutoRegister**.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="74caf-120">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="74caf-120">Property value/Return value</span></span>

<span data-ttu-id="74caf-121">返回可用于对**xlfUnregister**后续调用的函数 (**xltypeNum**)，注册 ID。</span><span class="sxs-lookup"><span data-stu-id="74caf-121">Returns the register ID of the function (**xltypeNum**), which can be used in subsequent calls to **xlfUnregister**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="74caf-122">备注</span><span class="sxs-lookup"><span data-stu-id="74caf-122">Remarks</span></span>

<span data-ttu-id="74caf-123">您不希望担心维护一个注册 ID，但您需要一个更高版本用于注销时，此函数很有用。</span><span class="sxs-lookup"><span data-stu-id="74caf-123">This function is useful when you do not want to worry about maintaining a register ID, but you need one later for unregistering.</span></span> <span data-ttu-id="74caf-124">也是用于将分配给菜单、 工具和按钮时要分配的功能是在 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="74caf-124">It is also useful for assigning to menus, tools, and buttons when the function you want to assign is in a DLL.</span></span>
  
<span data-ttu-id="74caf-125">在具有已提供给**xlfRegister**有效_pxFunctionText_参数已注册 DLL 或 XLL 函数，也可以通过将_pxFunctionText_传递给函数**xlfEvaluate**获得其注册 ID。</span><span class="sxs-lookup"><span data-stu-id="74caf-125">Where a DLL or XLL function has been registered with a valid  _pxFunctionText_ argument having been supplied to **xlfRegister**, its register ID can also be obtained by passing the  _pxFunctionText_ to the function **xlfEvaluate**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="74caf-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74caf-126">See also</span></span>

- [<span data-ttu-id="74caf-127">注册</span><span class="sxs-lookup"><span data-stu-id="74caf-127">REGISTER</span></span>](xlfregister-form-1.md)
- [<span data-ttu-id="74caf-128">注销</span><span class="sxs-lookup"><span data-stu-id="74caf-128">UNREGISTER</span></span>](xlfunregister-form-1.md)
- [<span data-ttu-id="74caf-129">关键及有用的 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="74caf-129">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

