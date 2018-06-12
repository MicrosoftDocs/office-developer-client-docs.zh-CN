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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: e0474b81a6d24663fe85303efc8fe2fd62cfdd82
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773845"
---
# <a name="xlcoerce"></a>xlCoerce

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
将转换为一种类型的**XLOPER**/ 到另一个**XLOPER12**或查找工作表上单元格的值。 
  
```cs
Excel12(xlCoerce, LPXLOPER12 pxRes, 2, LPXLOPER12 pxSource, LPXLOPER12 pxDestType);
```

## <a name="parameters"></a>参数

 _pxSource_
  
源**XLOPER**/ 需要转换的**XLOPER12** 。 
  
 _pxDestType_(**xltypeInt**)
  
（可选）。 在结果类型的位掩码，愿意接受。 应使用按位**OR**运算符 (|) 来指定多个可能的类型。 如果省略此参数，则会转换为值类型**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil** （如果被引用的单元格为空） 和引用块之一的单个单元格的引用单元格均转换为**xltypeMulti**。 这样， **xlCoerce**最方便的方法，以查找单元格的值。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

返回被强制的值 （**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeNil**或**xltypeMulti**）。
  
## <a name="remarks"></a>备注

 **xlCoerce**无法转换**xltypeBigData**或**xltypeFlow**。 作为_pxDestType_传递**xltypeMissing**或**xltypeNil**类型等效于省略该参数。 在某些情况下，转换可能会失败。 例如，某些字符串不能转换为数字，而其他人可以。 
  
如果数组或多单元格引用转换为单值类型，则结果是顶部的左侧单元格或数组元素的值。
  
## <a name="example"></a>示例

下面的代码可以中找到`\SAMPLES\EXAMPLE\EXAMPLE.C`。 
  
> [!NOTE]
> **XlcAlert**函数隐式尝试将其参数转换为字符串，以便确实要删除如下所示的强制步骤，并**xInt**无法直接传递到**xlcAlert**。 一样**xlcAlert**命令宏，此代码时才有效正确从宏表调用。 
  
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



[xlset，则](xlset.md)


[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

