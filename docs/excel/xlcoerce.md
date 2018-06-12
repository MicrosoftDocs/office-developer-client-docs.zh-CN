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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: e0474b81a6d24663fe85303efc8fe2fd62cfdd82
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773845"
---
# <a name="xlcoerce"></a><span data-ttu-id="dfa07-104">xlCoerce</span><span class="sxs-lookup"><span data-stu-id="dfa07-104">xlCoerce</span></span>

 <span data-ttu-id="dfa07-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dfa07-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="dfa07-106">将转换为一种类型的**XLOPER**/ 到另一个**XLOPER12**或查找工作表上单元格的值。</span><span class="sxs-lookup"><span data-stu-id="dfa07-106">Converts one type of **XLOPER**/ **XLOPER12** to another, or looks up cell values on a sheet.</span></span> 
  
```cs
Excel12(xlCoerce, LPXLOPER12 pxRes, 2, LPXLOPER12 pxSource, LPXLOPER12 pxDestType);
```

## <a name="parameters"></a><span data-ttu-id="dfa07-107">参数</span><span class="sxs-lookup"><span data-stu-id="dfa07-107">Parameters</span></span>

 <span data-ttu-id="dfa07-108">_pxSource_</span><span class="sxs-lookup"><span data-stu-id="dfa07-108">_pxSource_</span></span>
  
<span data-ttu-id="dfa07-109">源**XLOPER**/ 需要转换的**XLOPER12** 。</span><span class="sxs-lookup"><span data-stu-id="dfa07-109">The source **XLOPER**/ **XLOPER12** that needs to be converted.</span></span> 
  
 <span data-ttu-id="dfa07-110">_pxDestType_(**xltypeInt**)</span><span class="sxs-lookup"><span data-stu-id="dfa07-110">_pxDestType_ (**xltypeInt**)</span></span>
  
<span data-ttu-id="dfa07-111">（可选）。</span><span class="sxs-lookup"><span data-stu-id="dfa07-111">(Optional).</span></span> <span data-ttu-id="dfa07-112">在结果类型的位掩码，愿意接受。</span><span class="sxs-lookup"><span data-stu-id="dfa07-112">A bit-mask of the resulting types you are willing to accept.</span></span> <span data-ttu-id="dfa07-113">应使用按位**OR**运算符 (|) 来指定多个可能的类型。</span><span class="sxs-lookup"><span data-stu-id="dfa07-113">You should use the bitwise **OR** operator ( | ) to specify multiple possible types.</span></span> <span data-ttu-id="dfa07-114">如果省略此参数，则会转换为值类型**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil** （如果被引用的单元格为空） 和引用块之一的单个单元格的引用单元格均转换为**xltypeMulti**。</span><span class="sxs-lookup"><span data-stu-id="dfa07-114">If this argument is omitted, references to single cells are converted to one of the value types **xltypeStr**, **xltypeNum**, **xltypeBool**, **xltypeErr**, **xltypeNil** (if the referred-to cell is empty), and references to blocks of cells are converted to **xltypeMulti**.</span></span> <span data-ttu-id="dfa07-115">这样， **xlCoerce**最方便的方法，以查找单元格的值。</span><span class="sxs-lookup"><span data-stu-id="dfa07-115">This makes **xlCoerce** the most convenient way to look up cell values.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="dfa07-116">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="dfa07-116">Property value/Return value</span></span>

<span data-ttu-id="dfa07-117">返回被强制的值 （**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil**或**xltypeMulti**）。</span><span class="sxs-lookup"><span data-stu-id="dfa07-117">Returns the coerced value (**xltypeStr**, **xltypeNum**, **xltypeBool**, **xltypeErr**, **xltypeNil**, or **xltypeMulti**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="dfa07-118">备注</span><span class="sxs-lookup"><span data-stu-id="dfa07-118">Remarks</span></span>

 <span data-ttu-id="dfa07-119">**xlCoerce**无法转换**xltypeBigData**或**xltypeFlow**。</span><span class="sxs-lookup"><span data-stu-id="dfa07-119">**xlCoerce** cannot convert to or from **xltypeBigData** or **xltypeFlow**.</span></span> <span data-ttu-id="dfa07-120">作为_pxDestType_传递**xltypeMissing**或**xltypeNil**类型等效于省略该参数。</span><span class="sxs-lookup"><span data-stu-id="dfa07-120">Passing an **xltypeMissing** or **xltypeNil** type as  _pxDestType_ is equivalent to omitting the argument.</span></span> <span data-ttu-id="dfa07-121">在某些情况下，转换可能会失败。</span><span class="sxs-lookup"><span data-stu-id="dfa07-121">Conversion can fail in some cases.</span></span> <span data-ttu-id="dfa07-122">例如，某些字符串不能转换为数字，而其他人可以。</span><span class="sxs-lookup"><span data-stu-id="dfa07-122">For example, some strings cannot be converted to numbers, whereas others can.</span></span> 
  
<span data-ttu-id="dfa07-123">如果数组或多单元格引用转换为单值类型，则结果是顶部的左侧单元格或数组元素的值。</span><span class="sxs-lookup"><span data-stu-id="dfa07-123">If an array or a multi-cell reference is converted to a single value type, the result is the value of the top left cell or array element.</span></span>
  
## <a name="example"></a><span data-ttu-id="dfa07-124">示例</span><span class="sxs-lookup"><span data-stu-id="dfa07-124">Example</span></span>

<span data-ttu-id="dfa07-125">下面的代码可以中找到`\SAMPLES\EXAMPLE\EXAMPLE.C`。</span><span class="sxs-lookup"><span data-stu-id="dfa07-125">The following code can be found in  `\SAMPLES\EXAMPLE\EXAMPLE.C`.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="dfa07-126">**XlcAlert**函数隐式尝试将其参数转换为字符串，以便确实要删除如下所示的强制步骤，并**xInt**无法直接传递到**xlcAlert**。</span><span class="sxs-lookup"><span data-stu-id="dfa07-126">The **xlcAlert** function implicitly tries to convert its argument to a string so that the coercion step shown here could in fact be removed, and **xInt** could be passed directly to **xlcAlert**.</span></span> <span data-ttu-id="dfa07-127">一样**xlcAlert**命令宏，此代码时才有效正确从宏表调用。</span><span class="sxs-lookup"><span data-stu-id="dfa07-127">As **xlcAlert** is a command macro, this code only works correctly when called from a macro sheet.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="dfa07-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfa07-128">See also</span></span>



[<span data-ttu-id="dfa07-129">xlset，则</span><span class="sxs-lookup"><span data-stu-id="dfa07-129">xlSet</span></span>](xlset.md)


[<span data-ttu-id="dfa07-130">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="dfa07-130">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

