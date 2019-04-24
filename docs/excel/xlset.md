---
title: xlSet
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlSet
keywords:
- xlset 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 121e6212-0692-4430-97be-4792b53719bf
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 0912c1d40882933778d0df927ceb9de773063444
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303855"
---
# <a name="xlset"></a>xlSet

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
快速将常量值放入单元格或区域。 有关详细信息, 请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中的 "xlSet 和包含数组公式的工作簿"。
  
```cs
Excel12(xlSet, LPXLOPER12 pxRes, 2, LPXLOPER12 pxReference, LPXLOPER pxValue);
```

## <a name="parameters"></a>参数

_pxReference_(**xltypeRef**或**xltypeSRef**)
  
描述目标单元格或单元格的矩形引用。 该引用必须描述相邻单元格, 因此在**xltypeRef** `val.mref.lpmref->count`中必须设置为1。 
  
_pxValue_
  
要放入一个或多个单元格中的值。 有关详细信息，请参阅“注解”部分。
  
## <a name="remarks"></a>注解

### <a name="pxvalue-argument"></a>pxValue 参数

_pxValue_可以是一个值, 也可以是一个数组。 如果是一个值, 则使用该值填充整个目标区域。 如果是数组 (**xltypeMulti**), 则将数组的元素放在矩形中的相应位置。
  
如果对第二个参数使用水平数组, 则将其向下复制以填充整个矩形。 如果使用垂直数组, 则填充整个矩形的权限是重复的。 如果使用的是矩形数组, 并且对于要将其放入的矩形区域而言太小, 该范围将填充 **#N/a**s。
  
如果目标区域小于源数组, 则会将这些值复制到目标区域的限制中, 并忽略额外的数据。
  
若要清除目标矩形的元素, 请在源数组中使用**xltypeNil**类型数组元素。 若要清除整个目标矩形, 请省略第二个参数。 
  
### <a name="restrictions"></a>条件

**xlSet**无法撤消。 此外, 它还会销毁可能以前可用的任何撤消信息。 
  
**xlSet**只能将常量 (而不是公式) 放入单元格。 
  
**xlSet**的行为与 Class 3 命令等效的函数;也就是说, 在 dll 中的对象、宏、菜单、工具栏、快捷键或 "**运行**" 按钮 (从 Excel 2007 启动的功能区上的 "**视图**" 选项**** 卡中访问该对话框) 中调用 dll 时, 它将仅在 dll 内可用, 并且这些**工具**早期版本中的菜单)。 
  
## <a name="example"></a>示例

下面的示例使用从宏传入的值填充 B205: B206。 此命令函数示例需要一个参数, 因此仅当从 XLM 宏工作表调用, 或使用**Application. Run**方法从 VBA 模块中调用时, 才会执行此操作。 
  
`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlSetExample(short int iVal)
{
   XLOPER12 xRef, xValue;
   xRef.xltype = xltypeSRef;
   xRef.val.sref.count = 1;
   xRef.val.sref.ref.rwFirst = 204;
   xRef.val.sref.ref.rwLast = 205;
   xRef.val.sref.ref.colFirst = 1;
   xRef.val.sref.ref.colLast = 1;
   xValue.xltype = xltypeInt;
   xValue.val.w = iVal;
   Excel12(xlSet, 0, 2, (LPXLOPER12)&xRef, (LPXLOPER12)&xValue);
   return 1;
}
```

## <a name="see-also"></a>另请参阅

- [xlCoerce](xlcoerce.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

