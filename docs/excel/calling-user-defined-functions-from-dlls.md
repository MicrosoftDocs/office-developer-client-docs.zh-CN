---
title: 从 Dll 调用用户定义函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- udf [excel 2007]，从 dll，用户定义的函数 [Excel 2007] 中，从 Dll，Dll [Excel 2007] 中，调用 Udf 调用调用
localization_priority: Normal
ms.assetid: 99a37108-0083-4240-9c6a-3afa8d7a04f6
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4e893cf1e54489610315dd5c5d57bd78c3c936d0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773645"
---
# <a name="calling-user-defined-functions-from-dlls"></a><span data-ttu-id="18baf-104">从 Dll 调用用户定义函数</span><span class="sxs-lookup"><span data-stu-id="18baf-104">Calling user-defined functions from DLLs</span></span>

<span data-ttu-id="18baf-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18baf-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="18baf-106">从工作表中调用用户定义函数 (Udf) 是像调用内置函数一样简单： 通过单元格公式输入函数。</span><span class="sxs-lookup"><span data-stu-id="18baf-106">Calling user-defined functions (UDFs) from a worksheet is as simple as calling built-in functions: You enter the function via a cell formula.</span></span> <span data-ttu-id="18baf-107">但是，从 C API，没有预定义的函数代码用于回电。</span><span class="sxs-lookup"><span data-stu-id="18baf-107">However, from the C API, there are no pre-defined function codes to use with the call-backs.</span></span> <span data-ttu-id="18baf-108">若要使您能够调用 Udf，C API 导出的仅 XLL 函数， [xlUDF](xludf.md)函数。</span><span class="sxs-lookup"><span data-stu-id="18baf-108">To enable you to call UDFs, the C API exports an XLL-only function, the [xlUDF ](xludf.md) function.</span></span> <span data-ttu-id="18baf-109">函数的第一个参数是字符串形式的函数名称和后续参数是那些通常会所有 UDF。</span><span class="sxs-lookup"><span data-stu-id="18baf-109">The function's first argument is the function name as a string, and subsequent arguments are those that the UDF would normally expect.</span></span> 
  
<span data-ttu-id="18baf-110">可以通过使用参数 44 **xlfGetWorkspace**函数来获取当前注册的 XLL 加载项函数和命令的列表。</span><span class="sxs-lookup"><span data-stu-id="18baf-110">You can obtain a list of the currently registered XLL add-in functions and commands by using the **xlfGetWorkspace** function with the argument 44.</span></span> <span data-ttu-id="18baf-111">这将返回一个三列的数组，列表示下列：</span><span class="sxs-lookup"><span data-stu-id="18baf-111">This returns a three-column array where the columns represent the following:</span></span> 
  
- <span data-ttu-id="18baf-112">完整路径和的 XLL 的名称</span><span class="sxs-lookup"><span data-stu-id="18baf-112">The full path and name of the XLL</span></span>
    
- <span data-ttu-id="18baf-113">UDF 或命令，从 XLL 导出的名称</span><span class="sxs-lookup"><span data-stu-id="18baf-113">The name of the UDF or command as exported from the XLL</span></span>
    
- <span data-ttu-id="18baf-114">返回和参数的代码字符串</span><span class="sxs-lookup"><span data-stu-id="18baf-114">The return and argument code string</span></span>
    
> [!NOTE]
> <span data-ttu-id="18baf-115">从 XLL 导出名称可能不是按其 Excel 知道的 UDF 或命令的已注册名称相同。</span><span class="sxs-lookup"><span data-stu-id="18baf-115">The name as exported from the XLL might not be the same as the registered name by which Excel knows the UDF or command.</span></span> 
  
<span data-ttu-id="18baf-116">从 Excel 2007 开始，全面集成，分析工具库 (ATP) 函数，具有 C API 函数，如价格， **xlfPrice**自己枚举。</span><span class="sxs-lookup"><span data-stu-id="18baf-116">Starting in Excel 2007, the Analysis Toolpak (ATP) functions are fully integrated, and the C API has its own enumerations for functions such as PRICE, **xlfPrice**.</span></span> <span data-ttu-id="18baf-117">在早期版本中，您必须使用**xlUDF**调用这些函数。</span><span class="sxs-lookup"><span data-stu-id="18baf-117">In earlier versions, you had to use **xlUDF** to call these functions.</span></span> <span data-ttu-id="18baf-118">如果加载项需要使用 Excel 2003 和 Excel 2007 或更高版本，并使用这些功能，应检测当前版本，并以相应的方式调用的函数。</span><span class="sxs-lookup"><span data-stu-id="18baf-118">If your add-in needs to work with Excel 2003 and Excel 2007 or later versions, and it uses these functions, you should detect the current version and call the function in the appropriate way.</span></span> 
  
## <a name="examples"></a><span data-ttu-id="18baf-119">示例</span><span class="sxs-lookup"><span data-stu-id="18baf-119">Examples</span></span>

<span data-ttu-id="18baf-120">下面的示例演示用于运行版本的 Excel 2003 或更早版本时调用 ATP 函数**PRICE** **xlUDF**函数。</span><span class="sxs-lookup"><span data-stu-id="18baf-120">The following example shows the **xlUDF** function being used to call the ATP function **PRICE** when the running version of Excel is 2003 or earlier.</span></span> <span data-ttu-id="18baf-121">有关设置的全局版本变量，如**gExcelVersion12plus**在此示例中，请参阅[向后兼容性](backward-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="18baf-121">For information about the setting of a global version variable, such as **gExcelVersion12plus** in this example, see [Backward Compatibility](backward-compatibility.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="18baf-122">此示例使用框架函数**TempNum**， **TempStrConst**设置参数和 Excel 调用 C API。</span><span class="sxs-lookup"><span data-stu-id="18baf-122">This example uses the Framework functions **TempNum**, **TempStrConst** to set up the arguments and Excel to call the C API.</span></span> 
  
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

<span data-ttu-id="18baf-123">其中您正在呼叫通过修改就地**xlUDF**函数参数返回一个值，XLL 函数的结果**XLOPER/XLOPER12**地址通过仍然返回的值。</span><span class="sxs-lookup"><span data-stu-id="18baf-123">Where you are calling an XLL function that returns a value by modifying an argument in place, the **xlUDF** function still returns the value via the address of the result **XLOPER/XLOPER12**.</span></span> <span data-ttu-id="18baf-124">换句话说，就好像通过普通返回语句返回的结果。</span><span class="sxs-lookup"><span data-stu-id="18baf-124">In other words, the result is returned as if through a normal return statement.</span></span> <span data-ttu-id="18baf-125">对应于用于返回值的参数**XLOPER/XLOPER12**被修改。</span><span class="sxs-lookup"><span data-stu-id="18baf-125">The **XLOPER/XLOPER12** that corresponds to the argument that is used for the return value is unmodified.</span></span> <span data-ttu-id="18baf-126">例如，请考虑以下两个 Udf。</span><span class="sxs-lookup"><span data-stu-id="18baf-126">For example, consider the following two UDFs.</span></span> 
  
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

<span data-ttu-id="18baf-127">当**UDF\_2**呼叫**UDF\_1**、 到**Excel12**，在调用后**pxArg**的值不变，且由**UDF_1**返回的值包含在**xRetVal**。</span><span class="sxs-lookup"><span data-stu-id="18baf-127">When **UDF\_2** calls **UDF\_1**, the value of **pxArg** is unchanged after the call to **Excel12**, and the value returned by **UDF_1** is contained in **xRetVal**.</span></span>
  
<span data-ttu-id="18baf-128">在您调用 UDF 的大量这种方式，您可以使用[xlfEvaluate 函数](xlfevaluate.md)首先评估函数名称。</span><span class="sxs-lookup"><span data-stu-id="18baf-128">When you are making a large number of calls to a UDF in this way, you can evaluate the function name first by using the [xlfEvaluate function](xlfevaluate.md).</span></span> <span data-ttu-id="18baf-129">产生的号码，这是由**xlfRegister**函数返回的注册 ID 相同，可以传递代替函数名作为第一个参数给**xlUDF**函数。</span><span class="sxs-lookup"><span data-stu-id="18baf-129">The resulting number, which is the same as the registration ID that is returned by the **xlfRegister** function, can be passed in place of the function name as the first argument to the **xlUDF** function.</span></span> <span data-ttu-id="18baf-130">这使 Excel 查找和速度比它具有要查找的函数名称每次调用的函数。</span><span class="sxs-lookup"><span data-stu-id="18baf-130">This enables Excel to find and call the function more quickly than if it has to look up the function name every time.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="18baf-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18baf-131">See also</span></span>

- [<span data-ttu-id="18baf-132">在长时间的操作中允许用户中断</span><span class="sxs-lookup"><span data-stu-id="18baf-132">Permitting User Breaks in Lengthy Operations</span></span>](permitting-user-breaks-in-lengthy-operations.md)
- [<span data-ttu-id="18baf-133">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="18baf-133">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
- [<span data-ttu-id="18baf-134">Excel XLL SDK 入门</span><span class="sxs-lookup"><span data-stu-id="18baf-134">Getting Started with the Excel XLL SDK</span></span>](getting-started-with-the-excel-xll-sdk.md)

