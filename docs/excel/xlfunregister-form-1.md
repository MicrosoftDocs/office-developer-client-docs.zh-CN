---
title: xlfUnregister（窗体 1）
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfUnregister
keywords:
- xlfunregister 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 850bf65f-a151-44d6-b49f-d53ae2c83760
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3f5ebc08f89651331186990d8574e3150d4f484a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303890"
---
# <a name="xlfunregister-form-1"></a>xlfUnregister（窗体 1）

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
可从 DLL 或 XLL 命令调用, 该命令本身已由 Microsoft Excel 调用。 这相当于从 Excel XLM 宏表中调用 "**注销**"。 
  
可以在两种形式中调用**xlfUnregister** : 
  
- 表单 1: 注销单个命令或函数。
    
- 窗体 2: 卸载和停用 XLL。
    
在 Form 1 中调用, 此函数可减少以前使用**xlfRegister**或**REGISTER**注册的 DLL 函数或命令的使用次数。 如果使用计数已经为零, 则此函数不起作用。 当 dll 中所有函数的使用计数达到零时, dll 将从内存中卸载。
  
**xlfRegister**(窗体 1) 还定义了一个隐藏名称, 该名称是函数文本参数_pxFunctionText_, 其计算结果为函数或命令的注册 ID。 在注销函数时, 应使用**xlfSetName**删除此名称, 以使函数名称不再由函数向导列出。 有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
```cs
Excel4(xlfUnregister, LPXLOPER pxRes, 1, LPXLOPER pxRegisterId);
```

## <a name="parameters"></a>参数

_pxRegisterId_(**xltypeNum**)
  
要注销的函数的注册 ID。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功, 则返回**TRUE** (**xltypeBool**), 否则返回 FALSE。
  
## <a name="remarks"></a>注解

函数的注册 ID 在首次注册函数时由**xlfRegister**返回。 也可以通过调用[xlfRegisterId 函数](xlfregisterid.md)或[xlfEvaluate 函数](xlfevaluate.md)来获取它。 请注意, 如果函数尚未注册, xlfRegisterId 会尝试注册该函数。 因此, 如果您仅尝试获取 ID 以便注销该函数, 则最好通过将注册名称传递给**xlfEvaluate**来获取它。 如果函数尚未注册, **xlfEvaluate**将失败并 #NAME？误差. 
  
## <a name="example"></a>示例

请参阅中`\SAMPLES\GENERIC\GENERIC.C`的**fExit**函数的代码。
  
```cs
int WINAPI fExit(void)
{
   XLOPER12  xDLL,    // The name of this DLL //
   xFunc,             // The name of the function //
   xRegId;            // The registration ID //
   int i;
//
// This code gets the DLL name. It then uses this along with information
// from g_rgFuncs[] to obtain a REGISTER.ID() for each function. The
// register ID is then used to unregister each function. Then the code
// frees the DLL name and calls xlAutoClose.
//
   // Make xFunc a string //
   xFunc.xltype = xltypeStr;
   Excel12f(xlGetName, &xDLL, 0);
   for (i = 0; i < g_rgWorksheetFuncsRows; i++)
   {
      xFunc.val.str = (LPWSTR) (g_rgWorksheetFuncs[i][0]);
      Excel12f(xlfRegisterId,&xRegId,2,(LPXLOPER12)&xDLL,(LPXLOPER12)&xFunc);
      Excel12f(xlfUnregister, 0, 1, (LPXLOPER12) &xRegId);
   }
   for (i = 0; i < g_rgCommandFuncsRows; i++)
   {
      xFunc.val.str = (LPWSTR) (g_rgCommandFuncs[i][0]);
      Excel12f(xlfRegisterId,&xRegId,2,(LPXLOPER12)&xDLL,(LPXLOPER12)&xFunc);
      Excel12f(xlfUnregister, 0, 1, (LPXLOPER12) &xRegId);
   }
   Excel12f(xlFree, 0, 1,  (LPXLOPER12) &xDLL);
   return xlAutoClose();
}
```

## <a name="see-also"></a>另请参阅

- [xlfRegister（窗体 1）](xlfregister-form-1.md)
- [xlfRegisterId](xlfregisterid.md)
- [xlfUnregister（窗体 2）](xlfunregister-form-2.md)
- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

