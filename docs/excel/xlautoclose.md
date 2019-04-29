---
title: xlAutoClose
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoClose
keywords:
- xlautoclose 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 147e46cd-d4d7-49eb-acdc-5a2ebc2fb6c2
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e27ac922c4ba53a30e8e485d3210acc62b7d4bd3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415857"
---
# <a name="xlautoclose"></a>xlAutoClose

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
每当 XLL 停用时由 Microsoft Excel 调用。 加载项在 Excel 会话正常结束时停用。 加载项可在 Excel 会话期间由用户停用，在这种情况下，将调用此函数。
  
Excel 不需要 XLL 实施和导出此函数，尽管建议执行此操作，以便你的 XLL 可以取消注册函数和命令、释放资源、撤销自定义项等。 如果函数和命令未通过 XLL 显式取消注册，则 Excel 将在调用 **xlAutoClose** 函数后执行此操作。 
  
```cs
int WINAPI xlAutoClose(void);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数的实现必须返回 1 (**int**)。
  
## <a name="remarks"></a>说明

每当 XLL 停用时，Excel 就会调用 **xlAutoClose** 函数，即，从内存中卸载。 在以下情况下将停用 XLL： 
  
- 在 Excel 会话期间的会话正常结束时处于活动状态。
    
- 如果在 Excel 会话过程中显式卸载。
    
- 有几种方式可以卸载 XLL：
    
- 使用加载项管理器。
    
- 从调用 [xlfUnregister](xlfunregister-form-1.md) 的另一个 XLL，其中此 DLL 的名称作为唯一参数。 
    
- 从调用 [UNREGISTER](xlfunregister-form-1.md) 的 XLM 宏表，其中此 DLL 的名称作为唯一参数。 
    
此函数应执行以下操作：
  
- 删除由 XLL 添加的任何菜单或菜单项。
    
- 执行任何必需的全局清除。
    
- 删除已创建的任何名称，尤其是导出的函数的名称。 请注意，如果 **REGISTER** 的第四个参数存在，则注册函数可能导致创建某些名称。 
    
## <a name="example"></a>示例

查看文件 `SAMPLES\EXAMPLE\EXAMPLE.C` 和 `SAMPLES\GENERIC\GENERIC.C`，了解此函数的示例实现。 以下代码来自 `SAMPLES\GENERIC\GENERIC.C`。
  
```cs
int WINAPI xlAutoClose(void)
{
   int i;
   XLOPER12 xRes;
//
// This block first deletes all names added by xlAutoOpen or
// xlAutoRegister12. Next, it checks if the drop-down menu Generic still
// exists. If it does, it is deleted using xlfDeleteMenu. It then checks
// if the Test toolbar still exists. If it is, xlfDeleteToolbar is
// used to delete it.
//
// The following code to delete the defined names
// does not work in the current version of Excel. 
// You cannot delete these names once they are Registered.
// The code is left here in case the functionality becomes 
// available in a future version.
//
   for (i = 0; i < g_rgWorksheetFuncsRows; i++)
      Excel12f(xlfSetName, 0, 1, TempStr12(g_rgWorksheetFuncs[i][2]));
   for (i = 0; i < g_rgCommandFuncsRows; i++)
      Excel12f(xlfSetName, 0, 1, TempStr12(g_rgCommandFuncs[i][2]));
//
// Everything else works as documented.
//
   Excel12f(xlfGetBar, &amp;xRes, 3, TempInt12(10), TempStr12(L"Generic"), TempInt12(0));
   if (xRes.xltype != xltypeErr)
   {
      Excel12f(xlfDeleteMenu, 0, 2, TempNum12(10), TempStr12(L"Generic"));
      // Free the XLOPER12 returned by xlfGetBar //
      Excel12f(xlFree, 0, 1, (LPXLOPER12) &amp;xRes);
   }
   Excel12f(xlfGetToolbar, &amp;xRes, 2, TempInt12(7), TempStr12(L"Test"));
   if (xRes.xltype != xltypeErr)
   {
      Excel12f(xlfDeleteToolbar, 0, 1, TempStr12(L"Test"));
      // Free the XLOPER12 returned by xlfGetToolbar //
      Excel12f(xlFree, 0, 1, (LPXLOPER12) &amp;xRes);
   }
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[xlAutoOpen](xlautoopen.md)


[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

