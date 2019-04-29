---
title: 从 DLL 调用用户定义的函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- udf [excel 2007], 从 dll 调用, 用户定义的函数 [excel 2007], 从 dll 调用, dll [excel 2007], 调用 udf
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
# <a name="calling-user-defined-functions-from-dlls"></a><span data-ttu-id="f0060-104">从 DLL 调用用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="f0060-104">Calling user-defined functions from DLLs</span></span>

<span data-ttu-id="f0060-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f0060-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="f0060-106">从工作表调用用户定义的函数 (udf) 就像调用内置函数一样简单: 通过单元格公式输入函数。</span><span class="sxs-lookup"><span data-stu-id="f0060-106">Calling user-defined functions (UDFs) from a worksheet is as simple as calling built-in functions: You enter the function via a cell formula.</span></span> <span data-ttu-id="f0060-107">但是, 从 C API, 没有预定义的函数代码可用于回调。</span><span class="sxs-lookup"><span data-stu-id="f0060-107">However, from the C API, there are no pre-defined function codes to use with the call-backs.</span></span> <span data-ttu-id="f0060-108">为了使您能够调用 udf, C API 将导出仅 XLL 函数, 即[xlUDF](xludf.md)函数。</span><span class="sxs-lookup"><span data-stu-id="f0060-108">To enable you to call UDFs, the C API exports an XLL-only function, the [xlUDF ](xludf.md) function.</span></span> <span data-ttu-id="f0060-109">函数的第一个参数是一个字符串形式的函数名称, 而后面的参数是 UDF 通常需要的参数。</span><span class="sxs-lookup"><span data-stu-id="f0060-109">The function's first argument is the function name as a string, and subsequent arguments are those that the UDF would normally expect.</span></span> 
  
<span data-ttu-id="f0060-110">您可以通过使用带参数44的**xlfGetWorkspace**函数来获取当前注册的 XLL 加载项函数和命令的列表。</span><span class="sxs-lookup"><span data-stu-id="f0060-110">You can obtain a list of the currently registered XLL add-in functions and commands by using the **xlfGetWorkspace** function with the argument 44.</span></span> <span data-ttu-id="f0060-111">这将返回一个包含三列的数组, 其中的列表示以下内容:</span><span class="sxs-lookup"><span data-stu-id="f0060-111">This returns a three-column array where the columns represent the following:</span></span> 
  
- <span data-ttu-id="f0060-112">XLL 的完整路径和名称</span><span class="sxs-lookup"><span data-stu-id="f0060-112">The full path and name of the XLL</span></span>
    
- <span data-ttu-id="f0060-113">从 XLL 导出的 UDF 或命令的名称</span><span class="sxs-lookup"><span data-stu-id="f0060-113">The name of the UDF or command as exported from the XLL</span></span>
    
- <span data-ttu-id="f0060-114">return 和参数代码字符串</span><span class="sxs-lookup"><span data-stu-id="f0060-114">The return and argument code string</span></span>
    
> [!NOTE]
> <span data-ttu-id="f0060-115">从 XLL 导出的名称可能与 Excel 知道 UDF 或命令的注册名称不相同。</span><span class="sxs-lookup"><span data-stu-id="f0060-115">The name as exported from the XLL might not be the same as the registered name by which Excel knows the UDF or command.</span></span> 
  
<span data-ttu-id="f0060-116">从 Excel 2007 开始, 分析工具库 (ATP) 函数是完全集成的, 而 C API 对 PRICE、 **xlfPrice**等函数有自己的枚举。</span><span class="sxs-lookup"><span data-stu-id="f0060-116">Starting in Excel 2007, the Analysis Toolpak (ATP) functions are fully integrated, and the C API has its own enumerations for functions such as PRICE, **xlfPrice**.</span></span> <span data-ttu-id="f0060-117">在早期版本中, 您必须使用**xlUDF**调用这些函数。</span><span class="sxs-lookup"><span data-stu-id="f0060-117">In earlier versions, you had to use **xlUDF** to call these functions.</span></span> <span data-ttu-id="f0060-118">如果你的外接程序需要使用 excel 2003 和 excel 2007 或更高版本, 并且它使用了这些函数, 则应检测当前版本并以适当的方式调用函数。</span><span class="sxs-lookup"><span data-stu-id="f0060-118">If your add-in needs to work with Excel 2003 and Excel 2007 or later versions, and it uses these functions, you should detect the current version and call the function in the appropriate way.</span></span> 
  
## <a name="examples"></a><span data-ttu-id="f0060-119">示例</span><span class="sxs-lookup"><span data-stu-id="f0060-119">Examples</span></span>

<span data-ttu-id="f0060-120">下面的示例演示在 Excel 的运行版本为2003或更早版本时, 用于调用 ATP 函数**价格**的**xlUDF**函数。</span><span class="sxs-lookup"><span data-stu-id="f0060-120">The following example shows the **xlUDF** function being used to call the ATP function **PRICE** when the running version of Excel is 2003 or earlier.</span></span> <span data-ttu-id="f0060-121">有关全局版本变量的设置的信息 (如本示例中的**gExcelVersion12plus** ), 请参阅[向后兼容](backward-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="f0060-121">For information about the setting of a global version variable, such as **gExcelVersion12plus** in this example, see [Backward Compatibility](backward-compatibility.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0060-122">此示例使用 Framework 函数**TempNum**、 **TempStrConst**设置参数和 Excel, 以调用 C API。</span><span class="sxs-lookup"><span data-stu-id="f0060-122">This example uses the Framework functions **TempNum**, **TempStrConst** to set up the arguments and Excel to call the C API.</span></span> 
  
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

<span data-ttu-id="f0060-123">在调用通过就地修改参数返回值的 XLL 函数时, **xlUDF**函数仍通过 result **XLOPER/XLOPER12**的地址返回值。</span><span class="sxs-lookup"><span data-stu-id="f0060-123">Where you are calling an XLL function that returns a value by modifying an argument in place, the **xlUDF** function still returns the value via the address of the result **XLOPER/XLOPER12**.</span></span> <span data-ttu-id="f0060-124">换言之, 返回的结果就像通过正常的 return 语句那样。</span><span class="sxs-lookup"><span data-stu-id="f0060-124">In other words, the result is returned as if through a normal return statement.</span></span> <span data-ttu-id="f0060-125">与用于返回值的参数对应的**XLOPER/XLOPER12**不会被修改。</span><span class="sxs-lookup"><span data-stu-id="f0060-125">The **XLOPER/XLOPER12** that corresponds to the argument that is used for the return value is unmodified.</span></span> <span data-ttu-id="f0060-126">例如, 请考虑下面两个 udf。</span><span class="sxs-lookup"><span data-stu-id="f0060-126">For example, consider the following two UDFs.</span></span> 
  
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

<span data-ttu-id="f0060-127">**\_udf 2**调用**udf\_1**时, **pxArg**的值在调用**Excel12**后保持不变, **UDF_1**返回的值包含在**xRetVal**中。</span><span class="sxs-lookup"><span data-stu-id="f0060-127">When **UDF\_2** calls **UDF\_1**, the value of **pxArg** is unchanged after the call to **Excel12**, and the value returned by **UDF_1** is contained in **xRetVal**.</span></span>
  
<span data-ttu-id="f0060-128">以这种方式对 UDF 进行大量调用时, 可以先使用[xlfEvaluate 函数](xlfevaluate.md)计算函数名称。</span><span class="sxs-lookup"><span data-stu-id="f0060-128">When you are making a large number of calls to a UDF in this way, you can evaluate the function name first by using the [xlfEvaluate function](xlfevaluate.md).</span></span> <span data-ttu-id="f0060-129">生成的数字与**xlfRegister**函数返回的注册 ID 相同, 可以传递给函数名称, 将其作为**xlUDF**函数的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="f0060-129">The resulting number, which is the same as the registration ID that is returned by the **xlfRegister** function, can be passed in place of the function name as the first argument to the **xlUDF** function.</span></span> <span data-ttu-id="f0060-130">这使 Excel 能够更快地查找和调用函数, 而不是每次都需要查找函数名称。</span><span class="sxs-lookup"><span data-stu-id="f0060-130">This enables Excel to find and call the function more quickly than if it has to look up the function name every time.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f0060-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0060-131">See also</span></span>

- [<span data-ttu-id="f0060-132">允许用户中断冗长操作</span><span class="sxs-lookup"><span data-stu-id="f0060-132">Permitting User Breaks in Lengthy Operations</span></span>](permitting-user-breaks-in-lengthy-operations.md)
- [<span data-ttu-id="f0060-133">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="f0060-133">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
- [<span data-ttu-id="f0060-134">Getting Started with the Excel XLL SDK</span><span class="sxs-lookup"><span data-stu-id="f0060-134">Getting Started with the Excel XLL SDK</span></span>](getting-started-with-the-excel-xll-sdk.md)

