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
# <a name="calling-user-defined-functions-from-dlls"></a>从 Dll 调用用户定义函数

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
从工作表中调用用户定义函数 (Udf) 是像调用内置函数一样简单： 通过单元格公式输入函数。 但是，从 C API，没有预定义的函数代码用于回电。 若要使您能够调用 Udf，C API 导出的仅 XLL 函数， [xlUDF](xludf.md)函数。 函数的第一个参数是字符串形式的函数名称和后续参数是那些通常会所有 UDF。 
  
可以通过使用参数 44 **xlfGetWorkspace**函数来获取当前注册的 XLL 加载项函数和命令的列表。 这将返回一个三列的数组，列表示下列： 
  
- 完整路径和的 XLL 的名称
    
- UDF 或命令，从 XLL 导出的名称
    
- 返回和参数的代码字符串
    
> [!NOTE]
> 从 XLL 导出名称可能不是按其 Excel 知道的 UDF 或命令的已注册名称相同。 
  
从 Excel 2007 开始，全面集成，分析工具库 (ATP) 函数，具有 C API 函数，如价格， **xlfPrice**自己枚举。 在早期版本中，您必须使用**xlUDF**调用这些函数。 如果加载项需要使用 Excel 2003 和 Excel 2007 或更高版本，并使用这些功能，应检测当前版本，并以相应的方式调用的函数。 
  
## <a name="examples"></a>示例

下面的示例演示用于运行版本的 Excel 2003 或更早版本时调用 ATP 函数**PRICE** **xlUDF**函数。 有关设置的全局版本变量，如**gExcelVersion12plus**在此示例中，请参阅[向后兼容性](backward-compatibility.md)。
  
> [!NOTE]
> 此示例使用框架函数**TempNum**， **TempStrConst**设置参数和 Excel 调用 C API。 
  
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

其中您正在呼叫通过修改就地**xlUDF**函数参数返回一个值，XLL 函数的结果**XLOPER/XLOPER12**地址通过仍然返回的值。 换句话说，就好像通过普通返回语句返回的结果。 对应于用于返回值的参数**XLOPER/XLOPER12**被修改。 例如，请考虑以下两个 Udf。 
  
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

当**UDF\_2**呼叫**UDF\_1**、 到**Excel12**，在调用后**pxArg**的值不变，且由**UDF_1**返回的值包含在**xRetVal**。
  
在您调用 UDF 的大量这种方式，您可以使用[xlfEvaluate 函数](xlfevaluate.md)首先评估函数名称。 产生的号码，这是由**xlfRegister**函数返回的注册 ID 相同，可以传递代替函数名作为第一个参数给**xlUDF**函数。 这使 Excel 查找和速度比它具有要查找的函数名称每次调用的函数。 
  
## <a name="see-also"></a>另请参阅

- [在长时间的操作中允许用户中断](permitting-user-breaks-in-lengthy-operations.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
- [Excel XLL SDK 入门](getting-started-with-the-excel-xll-sdk.md)

