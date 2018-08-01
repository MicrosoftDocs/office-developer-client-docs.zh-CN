---
title: 框架库中的函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- '[excel 2007] framework 库函数，函数 [Excel 2007，] Framework 库'
localization_priority: Normal
ms.assetid: 7d9a13fd-9a4c-423e-bb08-4a5be57c7905
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 1d3878e376f95be3b277f1bb1a59545eb0a631ac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773762"
---
# <a name="functions-in-the-framework-library"></a>框架库中的函数

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
创建框架库是为了帮助确保编写 Xll 更轻松。 它包括用于管理**XLOPER**简单函数/ **XLOPER12**内存，创建临时**XLOPER**/ **XLOPER12**，始终能够调用 Microsoft Excel 回调函数 （**Excel4**、 **Excel4v*** * Excel12 * *，* * Excel12v * *) 和打印调试上附加终端的字符串。
  
在此库中包含的功能有助于简化与以下内容类似的代码段。
  
```cs
XLOPER12 xMissing, xBool;
xMissing.xltype = xltypeMissing;
xBool.xltype = xltypeBool;
xBool.val.xbool = 0;
Excel12(xlcDisplay, 0, 2, (LPXLOPER12) &xMissing, (LPXLOPER12) &xBool);
```

简化的代码类似于下面的示例。
  
```cs
Excel12f(xlcDisplay, 0, 2, TempMissing12(), TempBool12(0));
```

Framework 库中包含以下功能：
  
||
|:-----|
|[debugPrintf](debugprintf.md) <br/> |
|**GetTempMemory** <br/> |
|**FreeAllTempMemory** <br/> |
|[InitFramework](initframework.md) <br/> |
|[QuitFramework](quitframework.md) <br/> |
   
|**用于 XLOPERs 函数**|**用于 XLOPER12s 函数**|
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
   
使用这些函数缩短编写 DLL 或 XLL 所需的时间量。 示例应用程序从开始开发泛型还缩短了开发时间。 使用通用。C 作为模板帮助设置 XLL 的框架，然后用您自己中替换现有代码。
  
临时**XLOPER**/ **XLOPER12**函数创建**XLOPER**/ **XLOPER12**值使用的内存从本地堆由 Framework 库。 **XLOPER**/ **XLOPER12**值保持有效，直到您调用**FreeAllTempMemory**函数或任一**Excel**或**Excel12f**函数。 （的**Excel**和**Excel12f**函数释放所有临时内存返回之前。） 
  
若要使用的框架库函数，您必须包括 FRAMEWRK。H C 代码文件，并添加 FRAMEWRK。C 或 FRMWRK32。LIB 文件复制到您的代码项目。
  
## <a name="see-also"></a>另请参阅

- [Excel XLL SDK API Function Reference](excel-xll-sdk-api-function-reference.md)

