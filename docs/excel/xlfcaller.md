---
title: xlfCaller
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfCaller
keywords:
- xlfcaller 函数 [excel 2007]
localization_priority: Normal
ms.assetid: de4b119c-ae2e-4207-9783-8d5692a4d052
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 92d2d1877d7b315d178ef1fa36b47bd5f9f8e661
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773838"
---
# <a name="xlfcaller"></a>xlfCaller

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
返回有关单元格、 单元格、 命令范围在菜单上，在工具栏上或调用 DLL 命令或函数当前正在运行的对象上的工具的信息。
  
|**从代码调用**|**返回**|
|:-----|:-----|
|DLL  <br/> |注册 id。  <br/> |
|单个单元格  <br/> |单个单元格的引用。  <br/> |
|多单元格的数组公式  <br/> |一个多单元格的引用。  <br/> |
|条件格式表达式  <br/> |对条件格式应用于的单元格的引用。  <br/> |
|菜单  <br/> | 四个元素单行数组：  <br/>  条形图的 id。  <br/>  菜单位置。  <br/>  子菜单位置。  <br/>  命令位置。  <br/> |
|工具栏  <br/> | 两个元素的单行数组：  <br/>  内置工具栏或自定义工具栏的工具栏名称工具栏数。  <br/>  在工具栏上的位置。  <br/> |
|Graphic 对象  <br/> |对象标识符 （对象名称） 中。  <br/> |
|在与 xlcOnEnter，关联的命令。输入，事件陷阱  <br/> |对正在输入的单元格的单元格的引用。  <br/> |
|在与 xlcOnDoubleclick，关联的命令。DOUBLECLICK，事件陷阱。  <br/> |单元格，双击 （不一定是活动单元格）。  <br/> |
|Auto_Open、 AutoClose、 Auto_Activate 或 Auto_Deactivate 宏  <br/> |调用的工作表的名称。  <br/> |
|未列出的其他方法  <br/> |#REF! 错误。  <br/> |
   
```cs
Excel12(xlfCaller, (LPXLOPER12) pxRes,0);
```

## <a name="property-valuereturn-value"></a>属性值/返回值

返回值是以下**XLOPER**之一/ **XLOPER12**数据类型： **xltypeRef**、 **xltypeSRef**、 **xltypeNum**、 **xltypeStr**、 **xltypeErr**或**xltypeMulti**。 由于这些类型的三个指向分配的内存， **xlfCaller**的返回值应总是释放[xlFree 函数](xlfree.md)调用中，当不再需要时。 
  
有关**XLOPERs**/ **XLOPER12s** ，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。
  
## <a name="remarks"></a>说明

此函数是可从 DLL/XLL 工作表函数调用仅非-工作表函数。 只能从命令或宏表等效调用其他 XLM 信息函数函数。
  
## <a name="example"></a>示例

 `\SAMPLES\EXAMPLE\EXAMPLE.C`. 此函数调用命令宏 (xlcSelect)，并将正常工作，仅当调用从宏表。
  
```cs
short WINAPI CallerExample(void)
{
   XLOPER12 xRes;
   Excel12(xlfCaller, &xRes, 0);
   Excel12(xlcSelect, 0, 1, (LPXLOPER12)&xRes);
   Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes);
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[基本的有用 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

