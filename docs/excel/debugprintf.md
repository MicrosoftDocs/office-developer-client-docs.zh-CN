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
ms.openlocfilehash: 08bde61573874c137b18856fd24d23b324a35328
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311002"
---
# <a name="debugprintf"></a>debugPrintf

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
通过 Windows SDK 函数**OutputDebugStringA**将以 null 结尾的字节字符串写入活动调试器的框架库函数。 如果应用程序没有调试器, 系统调试器将显示字符串。 如果应用程序没有调试器且系统调试器未处于活动状态, 则**debugPrintf**不会执行任何操作。 
  
此函数不返回值。
  
```cs
void WINAPI debugPrintf(LPSTR lpFormat, arguments);
```

## <a name="parameters"></a>参数

 _lpFormat (LPSTR)_
  
格式字符串, 遵循与**sprintf**函数一起使用的语法和规则。 
  
 _自_
  
与格式字符串匹配的零个或多个参数。
  
## <a name="example"></a>示例

此函数打印字符串以显示该控件已传递给它。 必须在编译之前定义 _debug 标志, 否则此函数将不执行任何操作。
  
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

