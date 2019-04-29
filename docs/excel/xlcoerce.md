---
title: xlCoerce
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlCoerce
keywords:
- xlcoerce 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 9d47c16c-a7e7-4998-b594-9cf001827b7b
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d84839535d5eb913ca8a62d631238e3330683d0e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424831"
---
# <a name="xlcoerce"></a><span data-ttu-id="477df-104">xlCoerce</span><span class="sxs-lookup"><span data-stu-id="477df-104">xlCoerce</span></span>

 <span data-ttu-id="477df-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="477df-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="477df-106">将一种类型的**XLOPER**/ **XLOPER12**转换为另一种, 或在工作表上查找单元格的值。</span><span class="sxs-lookup"><span data-stu-id="477df-106">Converts one type of **XLOPER**/ **XLOPER12** to another, or looks up cell values on a sheet.</span></span> 
  
```cs
Excel12(xlCoerce, LPXLOPER12 pxRes, 2, LPXLOPER12 pxSource, LPXLOPER12 pxDestType);
```

## <a name="parameters"></a><span data-ttu-id="477df-107">参数</span><span class="sxs-lookup"><span data-stu-id="477df-107">Parameters</span></span>

 <span data-ttu-id="477df-108">_pxSource_</span><span class="sxs-lookup"><span data-stu-id="477df-108">_pxSource_</span></span>
  
<span data-ttu-id="477df-109">需要转换的源**XLOPER**/ **XLOPER12** 。</span><span class="sxs-lookup"><span data-stu-id="477df-109">The source **XLOPER**/ **XLOPER12** that needs to be converted.</span></span> 
  
 <span data-ttu-id="477df-110">_pxDestType_(**xltypeInt**)</span><span class="sxs-lookup"><span data-stu-id="477df-110">_pxDestType_ (**xltypeInt**)</span></span>
  
<span data-ttu-id="477df-111">(可选)。</span><span class="sxs-lookup"><span data-stu-id="477df-111">(Optional).</span></span> <span data-ttu-id="477df-112">您愿意接受的结果类型的位掩码。</span><span class="sxs-lookup"><span data-stu-id="477df-112">A bit-mask of the resulting types you are willing to accept.</span></span> <span data-ttu-id="477df-113">应使用按位**OR**运算符 (|) 来指定多个可能的类型。</span><span class="sxs-lookup"><span data-stu-id="477df-113">You should use the bitwise **OR** operator ( | ) to specify multiple possible types.</span></span> <span data-ttu-id="477df-114">如果省略此参数, 则对单个单元格的引用将转换为值类型**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil** (如果被引用的单元格为空) 和对块的引用的单元格将转换为**xltypeMulti**。</span><span class="sxs-lookup"><span data-stu-id="477df-114">If this argument is omitted, references to single cells are converted to one of the value types **xltypeStr**, **xltypeNum**, **xltypeBool**, **xltypeErr**, **xltypeNil** (if the referred-to cell is empty), and references to blocks of cells are converted to **xltypeMulti**.</span></span> <span data-ttu-id="477df-115">这使得**xlCoerce**最方便地查找单元格的值。</span><span class="sxs-lookup"><span data-stu-id="477df-115">This makes **xlCoerce** the most convenient way to look up cell values.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="477df-116">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="477df-116">Property value/Return value</span></span>

<span data-ttu-id="477df-117">返回强制的值 (**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil**或**xltypeMulti**)。</span><span class="sxs-lookup"><span data-stu-id="477df-117">Returns the coerced value (**xltypeStr**, **xltypeNum**, **xltypeBool**, **xltypeErr**, **xltypeNil**, or **xltypeMulti**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="477df-118">说明</span><span class="sxs-lookup"><span data-stu-id="477df-118">Remarks</span></span>

 <span data-ttu-id="477df-119">**xlCoerce**无法转换为**xltypeBigData**或**xltypeFlow**。</span><span class="sxs-lookup"><span data-stu-id="477df-119">**xlCoerce** cannot convert to or from **xltypeBigData** or **xltypeFlow**.</span></span> <span data-ttu-id="477df-120">将**xltypeMissing**或**xltypeNil**类型作为_pxDestType_传递等效于省略该参数。</span><span class="sxs-lookup"><span data-stu-id="477df-120">Passing an **xltypeMissing** or **xltypeNil** type as  _pxDestType_ is equivalent to omitting the argument.</span></span> <span data-ttu-id="477df-121">在某些情况下转换可能会失败。</span><span class="sxs-lookup"><span data-stu-id="477df-121">Conversion can fail in some cases.</span></span> <span data-ttu-id="477df-122">例如, 某些字符串不能转换为数字, 而另一些则可以。</span><span class="sxs-lookup"><span data-stu-id="477df-122">For example, some strings cannot be converted to numbers, whereas others can.</span></span> 
  
<span data-ttu-id="477df-123">如果数组或多单元格引用转换为单个值类型, 则结果是左上角的单元格或数组元素的值。</span><span class="sxs-lookup"><span data-stu-id="477df-123">If an array or a multi-cell reference is converted to a single value type, the result is the value of the top left cell or array element.</span></span>
  
## <a name="example"></a><span data-ttu-id="477df-124">示例</span><span class="sxs-lookup"><span data-stu-id="477df-124">Example</span></span>

<span data-ttu-id="477df-125">可以在中`\SAMPLES\EXAMPLE\EXAMPLE.C`找到以下代码。</span><span class="sxs-lookup"><span data-stu-id="477df-125">The following code can be found in  `\SAMPLES\EXAMPLE\EXAMPLE.C`.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="477df-126">**xlcAlert**函数隐式尝试将其参数转换为字符串, 以便实际上可以删除此处显示的强制步骤, 并且**xInt**可以直接传递给**xlcAlert**。</span><span class="sxs-lookup"><span data-stu-id="477df-126">The **xlcAlert** function implicitly tries to convert its argument to a string so that the coercion step shown here could in fact be removed, and **xInt** could be passed directly to **xlcAlert**.</span></span> <span data-ttu-id="477df-127">由于**xlcAlert**是命令宏, 因此该代码在从宏表中调用时仅能正常工作。</span><span class="sxs-lookup"><span data-stu-id="477df-127">As **xlcAlert** is a command macro, this code only works correctly when called from a macro sheet.</span></span> 
  
```cs
short WINAPI xlCoerceExample(short iVal)
{
   XLOPER12 xStr, xInt, xDestType;
   xInt.xltype = xltypeInt;
   xInt.val.w = iVal;
   xDestType.xltype = xltypeInt;
   xDestType.val.w = xltypeStr;
   Excel12f(xlCoerce, &xStr, 2, (LPXLOPER12)&xInt, (LPXLOPER12)&xDestType);
   Excel12f(xlcAlert, 0, 1, (LPXLOPER12)&xStr);
   Excel12f(xlFree, 0, 1, (LPXLOPER12)&xStr);
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="477df-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="477df-128">See also</span></span>



[<span data-ttu-id="477df-129">xlSet</span><span class="sxs-lookup"><span data-stu-id="477df-129">xlSet</span></span>](xlset.md)


[<span data-ttu-id="477df-130">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="477df-130">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

