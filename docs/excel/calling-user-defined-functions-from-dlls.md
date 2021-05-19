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
# <a name="calling-user-defined-functions-from-dlls"></a>从 DLL 调用用户定义的函数

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
从工作表 (UDF) 用户定义的函数与调用内置函数一样简单：通过单元格公式输入函数。 但是，从 C API 中，没有用于调用的预定义函数代码。 为了使您能够调用 UDF，C API 导出了一个仅 XLL 函数 [xlUDF ](xludf.md) 函数。 函数的第一个参数是字符串形式的函数名称，后续参数是 UDF 通常预期的参数。 
  
可以通过将 **xlfGetWorkspace** 函数与参数 44 一同使用来获取当前注册的 XLL 加载项函数和命令的列表。 这将返回一个三列数组，其中列表示以下内容： 
  
- XLL 的完整路径和名称
    
- 从 XLL 导出的 UDF 或命令的名称
    
- 返回和参数代码字符串
    
> [!NOTE]
> 从 XLL 导出的名称可能与注册名称不同，Excel UDF 或命令。 
  
从 Excel 2007 开始，分析工具库 (ATP) 函数完全集成，并且 C API 具有其自己的函数枚举，如 **PRICE、xlfPrice。** 在早期版本中，您必须使用 **xlUDF** 调用这些函数。 如果您的外接程序需要与 Excel 2003 和 Excel 2007 或更高版本一起使用，并且它使用这些函数，您应该检测当前版本，并适当地调用 函数。 
  
## <a name="examples"></a>示例

下面的示例演示当运行版本的 Excel 为 2003 或更早版本时，用于调用 ATP 函数 **PRICE** 的 **xlUDF** 函数。 有关全局版本变量（如此示例中的 **gExcelVersion12plus）** 设置的信息，请参阅 [向后兼容性](backward-compatibility.md)。
  
> [!NOTE]
> 此示例使用 Framework 函数 **TempNum** **、TempStrConst** 设置参数Excel调用 C API。 
  
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

在调用通过就地修改参数返回值的 XLL 函数时 **，xlUDF** 函数仍通过结果 **XLOPER/XLOPER12** 的地址返回值。 换句话说，返回的结果就像通过普通返回语句一样。 与用于返回值的参数相对应的 **XLOPER/XLOPER12** 未经修改。 例如，请考虑以下两个 UDF。 
  
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

当 **UDF \_ 2** 调用 **UDF \_ 1** 时 **，pxArg** 的值在 **调用 Excel12** 后保持不变，UDF_1 返回的值包含在 **xRetVal 中**。 
  
通过这种方法对 UDF 进行大量调用时，可以先使用 [xlfEvaluate](xlfevaluate.md)函数评估函数名称。 生成的编号与 **xlfRegister** 函数返回的注册 ID 相同，可以传递函数名称作为 **xlUDF** 函数的第一个参数。 这Excel查找和调用函数比每次查找函数名称要快。 
  
## <a name="see-also"></a>另请参阅

- [允许用户中断冗长操作](permitting-user-breaks-in-lengthy-operations.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
- [Getting Started with the Excel XLL SDK](getting-started-with-the-excel-xll-sdk.md)

