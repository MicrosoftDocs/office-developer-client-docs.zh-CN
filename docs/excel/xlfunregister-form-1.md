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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3f5ebc08f89651331186990d8574e3150d4f484a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410082"
---
# <a name="xlfunregister-form-1"></a>xlfUnregister（窗体 1）

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
可以从 DLL 或 XLL 命令调用，该命令本身已由 Microsoft Excel。 这相当于从 XLM 宏表Excel **UNREGISTER。** 
  
**xlfUnregister** 可以两种形式调用： 
  
- 表单 1：取消注册单个命令或函数。
    
- 表单 2：卸载和停用 XLL。
    
此函数在窗体 1 中调用，可以减少以前使用 **xlfRegister** 或 REGISTER 注册的 DLL 函数或命令 **的使用计数**。 如果使用率计数已为零，则此函数不起作用。 当 DLL 中所有函数的使用计数达到零时，DLL 从内存中卸载。
  
**xlfRegister** (Form 1) 还定义了一个隐藏名称，该名称是函数 text 参数  _pxFunctionText_，计算结果为函数或命令的注册 ID。 在注销函数时，应该使用 **xlfSetName** 删除此名称，以便函数向导不再列出该函数名称。 有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
```cs
Excel4(xlfUnregister, LPXLOPER pxRes, 1, LPXLOPER pxRegisterId);
```

## <a name="parameters"></a>参数

_pxRegisterId_ (**xltypeNum**) 
  
要注销的函数的注册 ID。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，则返回 **xltypeBool** (TRUE，) 返回 FALSE。 
  
## <a name="remarks"></a>备注

函数的注册 ID 由 **xlfRegister** 在首次注册函数时返回。 它还可以通过调用 [xlfRegisterId](xlfregisterid.md) 函数或 [xlfEvaluate](xlfevaluate.md)函数获取。 请注意，如果尚未注册函数，xlfRegisterId 将尝试注册函数。 因此，如果仅尝试获取 ID 以便可以注销 函数，最好将注册的名称传递到 **xlfEvaluate** 来获取它。 如果函数尚未注册 **，xlfEvaluate** 将失败，#NAME？error。 
  
## <a name="example"></a>示例

请参阅 中的 **fExit 函数** 代码  `\SAMPLES\GENERIC\GENERIC.C` 。
  
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

