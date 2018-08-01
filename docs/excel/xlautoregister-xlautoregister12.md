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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e6430a54b0c0ed3b6e08d3c9256cae7dcde926ab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19773830"
---
# <a name="xlautoregisterxlautoregister12"></a>xlAutoRegister/xlAutoRegister12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
每当呼叫对进行了**注册**，XLM 函数或 C API 等效[xlfRegister 函数](xlfregister-form-1.md)，要所注册的函数的返回和参数类型与丢失，Excel 将调用[xlAutoRegister 函数](xlautoregister-xlautoregister12.md)。 它允许 XLL 搜索其内部导出的函数和命令来注册功能使用参数并返回指定类型的列表。
  
从 Excel 2007 开始，Excel 调用优先于**xlAutoRegister**函数**xlAutoRegister12**函数的操作，如果它通过 XLL 导出。 
  
Excel 不需要 XLL 实施和导出其中任一函数。
  
> [!NOTE]
> 如果**xlAutoRegister**/ **xlAutoRegister12**尝试函数注册无需提供参数和返回类型、 递归调用循环发生最终溢出调用堆栈和崩溃 Excel。 
  
```cs
LPXLOPER12 WINAPI xlAutoRegister12(LPXLOPER12 pxName);
LPXLOPER WINAPI xlAutoRegister(LPXLOPER pxName);
```

## <a name="parameters"></a>参数

 _pxName_(**xltypeStr**)
  
正在注册 XLL 函数的名称。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

函数应返回尝试注册 XLL 函数_pxName_使用**xlfRegister**函数的结果。 如果指定的函数不是 XLL 的导出之一，则应返回 **#VALUE ！** 错误，或**NULL** Excel 会将解释在 **#VALUE ！**。
  
## <a name="remarks"></a>说明

**XlAutoRegister**的实现应执行不区分大小写搜索通过 XLL 的内部函数和它导出查找具有传入的名称匹配的命令列表。 如果找到函数或命令，则**xlAutoRegister**应尝试注册它，使用**xlfRegister**函数，并确保提供告诉返回和参数的函数，以及任何其他所需类型的 Excel 的字符串有关函数的信息。 它应将返回到 Excel 到**xlfRegister**的调用返回的任何内容。 如果已成功注册的函数， **xlfRegister**将返回包含的函数的注册 ID **xltypeNum**值。 
  
### <a name="example"></a>示例

请参阅文件`SAMPLES\EXAMPLE\EXAMPLE.C`示例实现的此函数。 
  
## <a name="see-also"></a>另请参阅



[注册](xlfregister-form-1.md)
  
[注销](xlfunregister-form-1.md)

