---
title: xlset，则
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlSet
keywords:
- xlset，则函数 [excel 2007]
localization_priority: Normal
ms.assetid: 121e6212-0692-4430-97be-4792b53719bf
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 63f50e441f5d851677f36754a17bcd6403705239
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773870"
---
# <a name="xlset"></a>xlset，则

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
很快将常量值放入单元格或区域。 有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中的"xlset，则和带数组公式的工作簿"。
  
```cs
Excel12(xlSet, LPXLOPER12 pxRes, 2, LPXLOPER12 pxReference, LPXLOPER pxValue);
```

## <a name="parameters"></a>参数

_pxReference_（**xltypeRef**或**xltypeSRef**）
  
一个描述目标单元格的矩形引用。 引用必须描述相邻单元格，因此，在**xltypeRef** `val.mref.lpmref->count`必须设置为 1。 
  
_pxValue_
  
值或值放入单元格或单元格。 有关详细信息，请参阅"备注"部分。
  
## <a name="remarks"></a>备注

### <a name="pxvalue-argument"></a>pxValue 参数

_pxValue_可以是一个值或数组。 如果它是一个值，该值与填充整个目标区域。 如果它是一个数组 (**xltypeMulti**)，该数组的元素放入该矩形中的相应位置。
  
如果您的第二个参数中使用水平数组，它被重复下以填满整个矩形。 如果您使用垂直数组，它被重复右以填满整个矩形。 如果您使用的矩形的数组，并且它是要放入该矩形区域太小，则用 **# n/A**s 填充该区域。
  
如果目标区域小于源数组，值将被复制中最多的目标区域的限制和额外数据将被忽略。
  
若要清除的目标矩形元素，请使用源数组中的**xltypeNil**类型数组元素。 若要清除整个目标矩形，省略第二个参数。 
  
### <a name="restrictions"></a>限制

**xlset，则**无法撤消。 此外，它销毁可能已前可用的任何撤消信息。 
  
**xlset，则**可以将仅常量，不公式放入单元格。 
  
作为类 3 命令等效函数; **xlset，则**行为即，它是仅在 DLL 可用，DLL 调用从对象、 宏、 菜单、 工具栏、 快捷键或在 （从开始在 Excel 2007 和**工具功能区上的**视图**选项卡访问**宏**对话框的**运行**按钮时**菜单早期版本中的)。 
  
## <a name="example"></a>示例

下面的示例填充 B205:B206 从宏中传递的值。 此命令函数示例需要一个参数，并因此只能如果从 XLM 宏工作表，或从使用**Application.Run**方法 VBA 模块中调用。 
  
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

