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
ms.openlocfilehash: 6077027a27c054c5a5e65a751373c41a87cb3836
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773850"
---
# <a name="xlfunregister-form-1"></a>xlfUnregister（窗体 1）

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
可从 DLL 或 XLL 命令的本身已调用由 Microsoft Excel 进行调用。 这是等效于从 Excel XLM 宏工作表调用**注销**。 
  
可在两个窗体中调用**xlfUnregister** : 
  
- 窗体 1： 取消注册的单个命令或函数。
    
- 窗体 2： 卸载并停用 XLL。
    
此函数调用窗体 1 中，减少了 DLL 函数或使用**xlfRegister**或**注册**以前注册的命令使用的计数。 如果使用次数已为零，则此函数无效。 当使用数目 DLL 中的所有函数为零时，DLL 是从内存中卸载。
  
**xlfRegister**（窗体 1） 还定义隐藏的名称即函数文本参数， _pxFunctionText_，并对其进行计算函数或命令的注册 id。 时注销函数，应使用**xlfSetName**以便函数名称不再列出由函数向导中删除此名称。 有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。
  
```cs
Excel4(xlfUnregister, LPXLOPER pxRes, 1, LPXLOPER pxRegisterId);
```

## <a name="parameters"></a>参数

_pxRegisterId_(**xltypeNum**)
  
要取消注册函数注册 ID。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果成功，则返回**TRUE** (**xltypeBool**)，否则为将返回 FALSE。
  
## <a name="remarks"></a>说明

注册时的功能是第一个 ID 的函数将返回的**xlfRegister**注册。 也可以获得通过调用[xlfRegisterId 函数](xlfregisterid.md)或[xlfEvaluate 函数](xlfevaluate.md)。 请注意该 xlfRegisterId 尝试注册功能，如果尚未注册。 因此，如果只想要获取的 ID，以便可以取消注册函数，则最好获取通过将已注册的名称传递给**xlfEvaluate**。 如果尚未注册该函数， **xlfEvaluate**将失败并 #NAME？错误。 
  
## <a name="example"></a>示例

请参阅**fExit**函数中的代码`\SAMPLES\GENERIC\GENERIC.C`。
  
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
- [基本的有用 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

