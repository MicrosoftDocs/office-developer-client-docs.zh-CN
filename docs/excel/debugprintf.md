---
title: debugPrintf
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- debugPrintf
keywords:
- debugprintf 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 9ad541f6-0b35-4f50-926a-8940e3f8033a
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 25669cfc705e797b80be0fab590d809e8f1e3b5c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773638"
---
# <a name="debugprintf"></a>debugPrintf

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Null 结尾字节字符串写入 Windows SDK 函数**OutputDebugStringA**通过活动的调试器 framework 库函数。 如果应用程序不有任何调试器，系统将调试器将显示的字符串。 如果应用程序都有任何调试器和系统调试未处于活动状态，则**debugPrintf**无实际作用。 
  
此函数不返回值。
  
```cs
void WINAPI debugPrintf(LPSTR lpFormat, arguments);
```

## <a name="parameters"></a>参数

 _lpFormat (LPSTR)_
  
下面的语法和规则的与**sprintf**函数一起使用的格式字符串。 
  
 _参数_
  
要与格式字符串匹配的零个或多个参数。
  
## <a name="example"></a>示例

此函数打印显示控件已传递给它的字符串。 在编译之前，必须定义 _DEBUG 标志，否则此函数不执行任何操作。
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI debugPrintfExample(void)
{
#ifdef _DEBUG
   debugPrintf("Made it!\r");
#endif
   return 1;
}

```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

