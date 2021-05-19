---
title: xlAutoRegister/xlAutoRegister12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoRegister
keywords:
- xlautoregister 函数 [excel 2007]
localization_priority: Normal
ms.assetid: aa4673cf-8e97-4678-b8d4-6a74426334f9
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f043558f3f642001e9ba11ee5b18a2721c3dddfb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421163"
---
# <a name="xlautoregisterxlautoregister12"></a>xlAutoRegister/xlAutoRegister12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
Excel调用 XLM 函数 **REGISTER** 或 C API 等效 [xlfRegister](xlfregister-form-1.md)函数时调用 [xlAutoRegister](xlautoregister-xlautoregister12.md)函数，并且缺少函数的返回和参数类型。 它允许 XLL 搜索其导出函数和命令的内部列表，以使用参数注册函数并返回指定的类型。
  
从 2007 Excel，Excel调用 **xlAutoRegister12** 函数，如果 XLL 导出 **xlAutoRegister** 函数，则优先调用该函数。 
  
Excel不需要 XLL 来实现和导出其中任一函数。
  
> [!NOTE]
> 如果 **xlAutoRegister** /  **xlAutoRegister12** 尝试注册函数而不提供参数和返回类型，将发生递归调用循环，该循环最终会溢出调用堆栈，并Excel。 
  
```cs
LPXLOPER12 WINAPI xlAutoRegister12(LPXLOPER12 pxName);
LPXLOPER WINAPI xlAutoRegister(LPXLOPER pxName);
```

## <a name="parameters"></a>参数

 _pxName_ (**xltypeStr**) 
  
正在注册的 XLL 函数的名称。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数应返回尝试使用 **xlfRegister** 函数注册 XLL 函数 _pxName_ 的尝试结果。 如果指定的函数不是 XLL 的导出函数之一，则它应返回 **#VALUE！** error 或 **NULL，Excel** 将在 **#VALUE！ 解释。**
  
## <a name="remarks"></a>备注

**xlAutoRegister** 的实现应执行不区分大小写的搜索，搜索 XLL 导出的函数和命令的内部列表，以查找传入名称的匹配项。 如果找到函数或命令 **，xlAutoRegister** 应尝试使用 **xlfRegister** 函数进行注册，以确保提供用于通知 Excel 函数的返回和参数类型的字符串，以及有关该函数的其他任何所需信息。 然后，它应返回Excel **调用 xlfRegister 返回的任何** 结果。 如果函数注册成功 **，xlfRegister** 将返回包含函数的 Register ID 的 **xltypeNum** 值。 
  
### <a name="example"></a>示例

有关此  `SAMPLES\EXAMPLE\EXAMPLE.C` 函数的示例实现，请参阅 文件。 
  
## <a name="see-also"></a>另请参阅



[REGISTER](xlfregister-form-1.md)
  
[UNREGISTER](xlfunregister-form-1.md)

