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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 0912c1d40882933778d0df927ceb9de773063444
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404601"
---
# <a name="xlset"></a>xlSet

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
非常快速地将常量值放入单元格或区域。 有关详细信息，请参阅 Excel XLL 开发中的已知问题中的"xlSet 和包含数组公式的[工作簿"。](known-issues-in-excel-xll-development.md)
  
```cs
Excel12(xlSet, LPXLOPER12 pxRes, 2, LPXLOPER12 pxReference, LPXLOPER pxValue);
```

## <a name="parameters"></a>参数

_pxReference_ (**xltypeRef** 或 **xltypeSRef**) 
  
描述目标单元格的矩形引用。 引用必须描述相邻的单元格，以便 **xltypeRef** `val.mref.lpmref->count` 中必须设置为 1。 
  
_pxValue_
  
要放入单元格中的值。 有关详细信息，请参阅“注解”部分。
  
## <a name="remarks"></a>备注

### <a name="pxvalue-argument"></a>pxValue 参数

_pxValue_ 可以是值，也可以为数组。 如果是值，则使用该值填充整个目标区域。 如果它是 **xltypeMulti** (数组，) 元素将放入矩形中的相应位置。
  
如果将水平数组用于第二个参数，则向下复制该数组以填充整个矩形。 如果使用垂直数组，则向右复制该数组以填充整个矩形。 如果使用矩形数组，并且对于要放入的矩形区域来说太小，则使用 **#N/A** 填充该区域。
  
如果目标区域小于源数组，则最多复制目标区域限制的值，并忽略额外的数据。
  
若要清除目标矩形的元素，请使用源数组中的 **xltypeNil** 类型数组元素。 若要清除整个目标矩形，请省略第二个参数。 
  
### <a name="restrictions"></a>限制

**xlSet** 无法撤消。 此外，它销毁之前可能提供的任何撤消信息。 
  
**xlSet** 只能将常量而不是公式放入单元格中。 
  
**xlSet** 的行为与 Class 3 命令等效函数;也就是说，从从 Excel 2007 开始从功能区上的"视图"选项卡访问的"宏"对话框 (中的"运行"按钮和早期版本的) 中的"工具"菜单调用 DLL 时，仅在 DLL 内可用。  
  
## <a name="example"></a>示例

下面的示例使用从宏传入的值填充 B205：B206。 此命令函数示例需要参数，因此仅在从 XLM 宏工作表或使用 **Application.Run** 方法的 VBA 模块调用时适用。 
  
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

