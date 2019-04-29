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
# <a name="calling-user-defined-functions-from-dlls"></a>从 DLL 调用用户定义的函数

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
从工作表调用用户定义的函数 (udf) 就像调用内置函数一样简单: 通过单元格公式输入函数。 但是, 从 C API, 没有预定义的函数代码可用于回调。 为了使您能够调用 udf, C API 将导出仅 XLL 函数, 即[xlUDF](xludf.md)函数。 函数的第一个参数是一个字符串形式的函数名称, 而后面的参数是 UDF 通常需要的参数。 
  
您可以通过使用带参数44的**xlfGetWorkspace**函数来获取当前注册的 XLL 加载项函数和命令的列表。 这将返回一个包含三列的数组, 其中的列表示以下内容: 
  
- XLL 的完整路径和名称
    
- 从 XLL 导出的 UDF 或命令的名称
    
- return 和参数代码字符串
    
> [!NOTE]
> 从 XLL 导出的名称可能与 Excel 知道 UDF 或命令的注册名称不相同。 
  
从 Excel 2007 开始, 分析工具库 (ATP) 函数是完全集成的, 而 C API 对 PRICE、 **xlfPrice**等函数有自己的枚举。 在早期版本中, 您必须使用**xlUDF**调用这些函数。 如果你的外接程序需要使用 excel 2003 和 excel 2007 或更高版本, 并且它使用了这些函数, 则应检测当前版本并以适当的方式调用函数。 
  
## <a name="examples"></a>示例

下面的示例演示在 Excel 的运行版本为2003或更早版本时, 用于调用 ATP 函数**价格**的**xlUDF**函数。 有关全局版本变量的设置的信息 (如本示例中的**gExcelVersion12plus** ), 请参阅[向后兼容](backward-compatibility.md)。
  
> [!NOTE]
> 此示例使用 Framework 函数**TempNum**、 **TempStrConst**设置参数和 Excel, 以调用 C API。 
  
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

在调用通过就地修改参数返回值的 XLL 函数时, **xlUDF**函数仍通过 result **XLOPER/XLOPER12**的地址返回值。 换言之, 返回的结果就像通过正常的 return 语句那样。 与用于返回值的参数对应的**XLOPER/XLOPER12**不会被修改。 例如, 请考虑下面两个 udf。 
  
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

**\_udf 2**调用**udf\_1**时, **pxArg**的值在调用**Excel12**后保持不变, **UDF_1**返回的值包含在**xRetVal**中。
  
以这种方式对 UDF 进行大量调用时, 可以先使用[xlfEvaluate 函数](xlfevaluate.md)计算函数名称。 生成的数字与**xlfRegister**函数返回的注册 ID 相同, 可以传递给函数名称, 将其作为**xlUDF**函数的第一个参数。 这使 Excel 能够更快地查找和调用函数, 而不是每次都需要查找函数名称。 
  
## <a name="see-also"></a>另请参阅

- [允许用户中断冗长操作](permitting-user-breaks-in-lengthy-operations.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
- [Getting Started with the Excel XLL SDK](getting-started-with-the-excel-xll-sdk.md)

