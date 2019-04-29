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
  
每当对 XLM 函数**REGISTER**或 C API 等效的[xlfRegister 函数](xlfregister-form-1.md)进行了调用时, Excel 将调用[xlAutoRegister 函数](xlautoregister-xlautoregister12.md), 其中包含要注册的函数的返回和参数类型。 它允许 XLL 搜索其导出函数和命令的内部列表, 以使用指定的参数和返回类型注册函数。
  
从 excel 2007 开始, 如果 XLL 导出了**xlAutoRegister**函数, excel 会在首选项中调用**xlAutoRegister12**函数。 
  
Excel 不需要 XLL 即可实现和导出这两个函数中的任何一个。
  
> [!NOTE]
> 如果**xlAutoRegister**/ **xlAutoRegister12**尝试在不提供参数和返回类型的情况下注册函数, 则会发生递归调用循环, 该循环最终会溢出调用堆栈并导致 Excel 崩溃。 
  
```cs
LPXLOPER12 WINAPI xlAutoRegister12(LPXLOPER12 pxName);
LPXLOPER WINAPI xlAutoRegister(LPXLOPER pxName);
```

## <a name="parameters"></a>参数

 _pxName_(**xltypeStr**)
  
正在注册的 XLL 函数的名称。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数应返回尝试使用**xlfRegister**函数注册 XLL 函数_pxName_的结果。 如果指定的函数不是 XLL 的导出之一, 它应返回 **#VALUE!** 错误或**NULL** , Excel 会将其解释 **#VALUE!**。
  
## <a name="remarks"></a>说明

您的**xlAutoRegister**实现应通过您在 XLL 的函数和命令导出的函数和命令的内部列表中执行不区分大小写的搜索, 以查找与传入的名称相匹配的函数和命令。 如果找到了函数或命令, **xlAutoRegister**应尝试使用**xlfRegister**函数注册它, 以确保提供一个字符串, 该字符串告诉 Excel 函数的返回类型和参数类型, 以及任何其他必需的有关函数的信息。 然后, 它应返回到 Excel 调用**xlfRegister**返回的任何内容。 如果函数已成功注册, **xlfRegister**将返回一个**xltypeNum**值, 其中包含函数的寄存器 ID。 
  
### <a name="example"></a>示例

有关此函数`SAMPLES\EXAMPLE\EXAMPLE.C`的示例实现, 请参阅文件。 
  
## <a name="see-also"></a>另请参阅



[注册表](xlfregister-form-1.md)
  
[注销](xlfunregister-form-1.md)

