---
title: 从 DLL 调用用户定义的函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- udfs [excel 2007]，从 dll 调用，用户定义函数 [Excel 2007]，从 DLL 调用 [Excel 2007]，调用 UDF
localization_priority: Normal
ms.assetid: 99a37108-0083-4240-9c6a-3afa8d7a04f6
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9e2ca3f4485fb41c5ab6a48f323b4c0093e747e4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417943"
---
# <a name="calling-user-defined-functions-from-dlls"></a><span data-ttu-id="9417c-104">从 DLL 调用用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="9417c-104">Calling user-defined functions from DLLs</span></span>

<span data-ttu-id="9417c-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9417c-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="9417c-106">从工作表 (UDF) 用户定义的函数与调用内置函数一样简单：通过单元格公式输入函数。</span><span class="sxs-lookup"><span data-stu-id="9417c-106">Calling user-defined functions (UDFs) from a worksheet is as simple as calling built-in functions: You enter the function via a cell formula.</span></span> <span data-ttu-id="9417c-107">但是，从 C API 中，没有用于调用的预定义函数代码。</span><span class="sxs-lookup"><span data-stu-id="9417c-107">However, from the C API, there are no pre-defined function codes to use with the call-backs.</span></span> <span data-ttu-id="9417c-108">为了使您能够调用 UDF，C API 导出了一个仅 XLL 函数 [xlUDF ](xludf.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="9417c-108">To enable you to call UDFs, the C API exports an XLL-only function, the [xlUDF ](xludf.md) function.</span></span> <span data-ttu-id="9417c-109">函数的第一个参数是字符串形式的函数名称，后续参数是 UDF 通常预期的参数。</span><span class="sxs-lookup"><span data-stu-id="9417c-109">The function's first argument is the function name as a string, and subsequent arguments are those that the UDF would normally expect.</span></span> 
  
<span data-ttu-id="9417c-110">可以通过将 **xlfGetWorkspace** 函数与参数 44 一同使用来获取当前注册的 XLL 加载项函数和命令的列表。</span><span class="sxs-lookup"><span data-stu-id="9417c-110">You can obtain a list of the currently registered XLL add-in functions and commands by using the **xlfGetWorkspace** function with the argument 44.</span></span> <span data-ttu-id="9417c-111">这将返回一个三列数组，其中列表示以下内容：</span><span class="sxs-lookup"><span data-stu-id="9417c-111">This returns a three-column array where the columns represent the following:</span></span> 
  
- <span data-ttu-id="9417c-112">XLL 的完整路径和名称</span><span class="sxs-lookup"><span data-stu-id="9417c-112">The full path and name of the XLL</span></span>
    
- <span data-ttu-id="9417c-113">从 XLL 导出的 UDF 或命令的名称</span><span class="sxs-lookup"><span data-stu-id="9417c-113">The name of the UDF or command as exported from the XLL</span></span>
    
- <span data-ttu-id="9417c-114">返回和参数代码字符串</span><span class="sxs-lookup"><span data-stu-id="9417c-114">The return and argument code string</span></span>
    
> [!NOTE]
> <span data-ttu-id="9417c-115">从 XLL 导出的名称可能与注册名称不同，Excel UDF 或命令。</span><span class="sxs-lookup"><span data-stu-id="9417c-115">The name as exported from the XLL might not be the same as the registered name by which Excel knows the UDF or command.</span></span> 
  
<span data-ttu-id="9417c-116">从 Excel 2007 开始，分析工具库 (ATP) 函数完全集成，并且 C API 具有其自己的函数枚举，如 **PRICE、xlfPrice。**</span><span class="sxs-lookup"><span data-stu-id="9417c-116">Starting in Excel 2007, the Analysis Toolpak (ATP) functions are fully integrated, and the C API has its own enumerations for functions such as PRICE, **xlfPrice**.</span></span> <span data-ttu-id="9417c-117">在早期版本中，您必须使用 **xlUDF** 调用这些函数。</span><span class="sxs-lookup"><span data-stu-id="9417c-117">In earlier versions, you had to use **xlUDF** to call these functions.</span></span> <span data-ttu-id="9417c-118">如果您的外接程序需要与 Excel 2003 和 Excel 2007 或更高版本一起使用，并且它使用这些函数，您应该检测当前版本，并适当地调用 函数。</span><span class="sxs-lookup"><span data-stu-id="9417c-118">If your add-in needs to work with Excel 2003 and Excel 2007 or later versions, and it uses these functions, you should detect the current version and call the function in the appropriate way.</span></span> 
  
## <a name="examples"></a><span data-ttu-id="9417c-119">示例</span><span class="sxs-lookup"><span data-stu-id="9417c-119">Examples</span></span>

<span data-ttu-id="9417c-120">下面的示例演示当运行版本的 Excel 为 2003 或更早版本时，用于调用 ATP 函数 **PRICE** 的 **xlUDF** 函数。</span><span class="sxs-lookup"><span data-stu-id="9417c-120">The following example shows the **xlUDF** function being used to call the ATP function **PRICE** when the running version of Excel is 2003 or earlier.</span></span> <span data-ttu-id="9417c-121">有关全局版本变量（如此示例中的 **gExcelVersion12plus）** 设置的信息，请参阅 [向后兼容性](backward-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="9417c-121">For information about the setting of a global version variable, such as **gExcelVersion12plus** in this example, see [Backward Compatibility](backward-compatibility.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9417c-122">此示例使用 Framework 函数 **TempNum** **、TempStrConst** 设置参数Excel调用 C API。</span><span class="sxs-lookup"><span data-stu-id="9417c-122">This example uses the Framework functions **TempNum**, **TempStrConst** to set up the arguments and Excel to call the C API.</span></span> 
  
```C
LPXLOPER TempNum(double d);
LPXLOPER TempStrConst(const LPSTR lpstr);
int cdecl Excel(int xlfn, LPXLOPER pxResult, int count, ...);
double call_ATP_example(void)
{
  XLOPER xPrice;
  int xl_ret_val;
  if(gExcelVersion12plus) // Starting in Excel 2007
  {
    xl_ret_val = Excel(xlfPrice, &xPrice, 7,
      TempNum(39084.0), // settlement date 2-Jan-2007
      TempNum(46706.0), // maturity date 15-Nov-2027
      TempNum(0.04), // Coupon
      TempNum(0.05), // Yield
      TempNum(1.0), // redemption value: 100% of face
      TempNum(1.0), // Annual coupons
      TempNum(1.0)); // Rate basis Act/Act
  }
  else // Excel 2003-
  {
    xl_ret_val = Excel(xlUDF, &xPrice, 8,
      TempStrConst("PRICE"),
      TempNum(39084.0), // settlement date 2-Jan-2007
      TempNum(46706.0), // maturity date 15-Nov-2027
      TempNum(0.04), // Coupon
      TempNum(0.05), // Yield
      TempNum(1.0), // redepmtion value: 100% of face
      TempNum(1.0), // Annual coupons
      TempNum(1.0)); // Rate basis Act/Act
  }
  if(xl_ret_val != xlretSuccess || xPrice.xltype != xltypeNum)
  {
// Even though PRICE is not expected to return a string, there
// is no harm in freeing the XLOPER to be safe
    Excel(xlFree, 0, 1, &xPrice);
    return -1.0; // an error value
  }
  return xPrice.val.num;
}
```

<br/>

<span data-ttu-id="9417c-123">在调用通过就地修改参数返回值的 XLL 函数时 **，xlUDF** 函数仍通过结果 **XLOPER/XLOPER12** 的地址返回值。</span><span class="sxs-lookup"><span data-stu-id="9417c-123">Where you are calling an XLL function that returns a value by modifying an argument in place, the **xlUDF** function still returns the value via the address of the result **XLOPER/XLOPER12**.</span></span> <span data-ttu-id="9417c-124">换句话说，返回的结果就像通过普通返回语句一样。</span><span class="sxs-lookup"><span data-stu-id="9417c-124">In other words, the result is returned as if through a normal return statement.</span></span> <span data-ttu-id="9417c-125">与用于返回值的参数相对应的 **XLOPER/XLOPER12** 未经修改。</span><span class="sxs-lookup"><span data-stu-id="9417c-125">The **XLOPER/XLOPER12** that corresponds to the argument that is used for the return value is unmodified.</span></span> <span data-ttu-id="9417c-126">例如，请考虑以下两个 UDF。</span><span class="sxs-lookup"><span data-stu-id="9417c-126">For example, consider the following two UDFs.</span></span> 
  
```C
// Registered as "1E". Returns its argument incremented by 1.
void WINAPI UDF_1(double *pArg)
{
  *pArg += 1.0;
}
// Registered as "QQ". Returns its argument unmodified
// unless it is a number, in which case it increments it
// by calling UDF_1.
LPXLOPER12 WINAPI UDF_2(LPXLOPER12 pxArg)
{
  static XLOPER12 xRetVal; // Not thread-safe
  XLOPER12 xFn;
  xFn.xltype = xltypeStr;
  xFn.val.str = L"\005UDF_1";
  Excel12(xlUDF, &xRetVal, 2, &xFn, pxArg);
  xRetVal.xltype |= xlbitXLFree;
  return &xRetVal;
}
```

<span data-ttu-id="9417c-127">当 **UDF \_ 2** 调用 **UDF \_ 1** 时 **，pxArg** 的值在 **调用 Excel12** 后保持不变，UDF_1 返回的值包含在 **xRetVal 中**。 </span><span class="sxs-lookup"><span data-stu-id="9417c-127">When **UDF\_2** calls **UDF\_1**, the value of **pxArg** is unchanged after the call to **Excel12**, and the value returned by **UDF_1** is contained in **xRetVal**.</span></span>
  
<span data-ttu-id="9417c-128">通过这种方法对 UDF 进行大量调用时，可以先使用 [xlfEvaluate](xlfevaluate.md)函数评估函数名称。</span><span class="sxs-lookup"><span data-stu-id="9417c-128">When you are making a large number of calls to a UDF in this way, you can evaluate the function name first by using the [xlfEvaluate function](xlfevaluate.md).</span></span> <span data-ttu-id="9417c-129">生成的编号与 **xlfRegister** 函数返回的注册 ID 相同，可以传递函数名称作为 **xlUDF** 函数的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="9417c-129">The resulting number, which is the same as the registration ID that is returned by the **xlfRegister** function, can be passed in place of the function name as the first argument to the **xlUDF** function.</span></span> <span data-ttu-id="9417c-130">这Excel查找和调用函数比每次查找函数名称要快。</span><span class="sxs-lookup"><span data-stu-id="9417c-130">This enables Excel to find and call the function more quickly than if it has to look up the function name every time.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9417c-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9417c-131">See also</span></span>

- [<span data-ttu-id="9417c-132">允许用户中断冗长操作</span><span class="sxs-lookup"><span data-stu-id="9417c-132">Permitting User Breaks in Lengthy Operations</span></span>](permitting-user-breaks-in-lengthy-operations.md)
- [<span data-ttu-id="9417c-133">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="9417c-133">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
- [<span data-ttu-id="9417c-134">Getting Started with the Excel XLL SDK</span><span class="sxs-lookup"><span data-stu-id="9417c-134">Getting Started with the Excel XLL SDK</span></span>](getting-started-with-the-excel-xll-sdk.md)

