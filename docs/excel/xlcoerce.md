---
title: xlCoerce
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlCoerce
keywords:
- xlcoerce 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 9d47c16c-a7e7-4998-b594-9cf001827b7b
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d84839535d5eb913ca8a62d631238e3330683d0e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424831"
---
# <a name="xlcoerce"></a>xlCoerce

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
将一种类型的**XLOPER**/ **XLOPER12**转换为另一种, 或在工作表上查找单元格的值。 
  
```cs
Excel12(xlCoerce, LPXLOPER12 pxRes, 2, LPXLOPER12 pxSource, LPXLOPER12 pxDestType);
```

## <a name="parameters"></a>参数

 _pxSource_
  
需要转换的源**XLOPER**/ **XLOPER12** 。 
  
 _pxDestType_(**xltypeInt**)
  
(可选)。 您愿意接受的结果类型的位掩码。 应使用按位**OR**运算符 (|) 来指定多个可能的类型。 如果省略此参数, 则对单个单元格的引用将转换为值类型**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil** (如果被引用的单元格为空) 和对块的引用的单元格将转换为**xltypeMulti**。 这使得**xlCoerce**最方便地查找单元格的值。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回强制的值 (**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil**或**xltypeMulti**)。
  
## <a name="remarks"></a>说明

 **xlCoerce**无法转换为**xltypeBigData**或**xltypeFlow**。 将**xltypeMissing**或**xltypeNil**类型作为_pxDestType_传递等效于省略该参数。 在某些情况下转换可能会失败。 例如, 某些字符串不能转换为数字, 而另一些则可以。 
  
如果数组或多单元格引用转换为单个值类型, 则结果是左上角的单元格或数组元素的值。
  
## <a name="example"></a>示例

可以在中`\SAMPLES\EXAMPLE\EXAMPLE.C`找到以下代码。 
  
> [!NOTE]
> **xlcAlert**函数隐式尝试将其参数转换为字符串, 以便实际上可以删除此处显示的强制步骤, 并且**xInt**可以直接传递给**xlcAlert**。 由于**xlcAlert**是命令宏, 因此该代码在从宏表中调用时仅能正常工作。 
  
```cs
short WINAPI xlCoerceExample(short iVal)
{
   XLOPER12 xStr, xInt, xDestType;
   xInt.xltype = xltypeInt;
   xInt.val.w = iVal;
   xDestType.xltype = xltypeInt;
   xDestType.val.w = xltypeStr;
   Excel12f(xlCoerce, &xStr, 2, (LPXLOPER12)&xInt, (LPXLOPER12)&xDestType);
   Excel12f(xlcAlert, 0, 1, (LPXLOPER12)&xStr);
   Excel12f(xlFree, 0, 1, (LPXLOPER12)&xStr);
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[xlSet](xlset.md)


[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

