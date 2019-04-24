---
title: 框架库中的函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- 框架库函数 [excel 2007], 函数 [excel 2007], 框架库
localization_priority: Normal
ms.assetid: 7d9a13fd-9a4c-423e-bb08-4a5be57c7905
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4eeb9e5db09592e98e9afb763efaa6be18eb2f7e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304051"
---
# <a name="functions-in-the-framework-library"></a>框架库中的函数

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
创建框架库旨在帮助简化编写 xll。 它包括用于管理**XLOPER**/ **XLOPER12**内存的简单函数、创建临时**XLOPER**/ **XLOPER12**、可靠地调用 Microsoft Excel 回调函数 (**Excel4**、 **Excel4v**、* * Excel12 * *、* * Excel12v * *), 并在附加的终端上打印调试字符串。
  
此库中包含的函数有助于简化如下所示的一段代码。
  
```cs
XLOPER12 xMissing, xBool;
xMissing.xltype = xltypeMissing;
xBool.xltype = xltypeBool;
xBool.val.xbool = 0;
Excel12(xlcDisplay, 0, 2, (LPXLOPER12) &xMissing, (LPXLOPER12) &xBool);
```

简化的代码如以下示例所示。
  
```cs
Excel12f(xlcDisplay, 0, 2, TempMissing12(), TempBool12(0));
```

框架库中包含以下函数:
  
||
|:-----|
|[debugPrintf](debugprintf.md) <br/> |
|**GetTempMemory** <br/> |
|**FreeAllTempMemory** <br/> |
|[InitFramework](initframework.md) <br/> |
|[QuitFramework](quitframework.md) <br/> |
   
|**用于 XLOPERs 的函数**|**用于 XLOPER12s 的函数**|
|:-----|:-----|
|[Excel](excel-excel12f.md) <br/> |[Excel12f](excel-excel12f.md) <br/> |
|[TempNum](tempnum-tempnum12.md) <br/> |[TempNum12](tempnum-tempnum12.md) <br/> |
|[TempStr](tempstr.md) <br/> |[TempStr12](tempstrconst-tempstr12.md) <br/> |
|[TempStrConst](tempstrconst-tempstr12.md) <br/> |[TempStr12Const](tempstrconst-tempstr12.md) <br/> |
|[TempBool](tempbool-tempbool12.md) <br/> |[TempBool12](tempbool-tempbool12.md) <br/> |
|[TempInt](tempint-tempint12.md) <br/> |[TempInt12](tempint-tempint12.md) <br/> |
|[TempErr](temperr-temperr12.md) <br/> |[TempErr12](temperr-temperr12.md) <br/> |
|[TempActiveRef](tempactiveref-tempactiveref12.md) <br/> |[TempActiveRef12](tempactiveref-tempactiveref12.md) <br/> |
|[TempActiveCell](tempactivecell-tempactivecell12.md) <br/> |[TempActiveCell12](tempactivecell-tempactivecell12.md) <br/> |
|[TempActiveRow](tempactiverow-tempactiverow12.md) <br/> |[TempActiveRow12](tempactiverow-tempactiverow12.md) <br/> |
|[TempActiveColumn](tempactivecolumn-tempactivecolumn12.md) <br/> |[TempActiveColumn12](tempactivecolumn-tempactivecolumn12.md) <br/> |
|[TempMissing](tempmissing-tempmissing12.md) <br/> |[TempMissing12](tempmissing-tempmissing12.md) <br/> |
   
使用这些函数可缩短写入 DLL 或 XLL 所需的时间量。 从示例应用程序开始开发一般也缩短了开发时间。 使用 GENERIC。C 作为模板来帮助设置 XLL 框架, 然后将现有代码替换为您自己的代码。
  
临时**XLOPER**/ **XLOPER12**函数使用由框架库管理的本地堆中的内存创建**XLOPER**/ **XLOPER12**值。 在调用**FreeAllTempMemory**函数或任一**Excel**或**Excel12f**函数之前, **XLOPER**/ **XLOPER12**值始终有效。 ( **Excel**和**Excel12f**函数在返回之前释放所有临时内存。) 
  
若要使用框架库函数, 必须包含 FRAMEWRK。H 文件, 并添加 FRAMEWRK。C 或 FRMWRK32。LIB 文件到代码项目。
  
## <a name="see-also"></a>另请参阅

- [Excel XLL SDK API Function Reference](excel-xll-sdk-api-function-reference.md)

