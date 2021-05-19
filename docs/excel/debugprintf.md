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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 08bde61573874c137b18856fd24d23b324a35328
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424796"
---
# <a name="debugprintf"></a>debugPrintf

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
通过 Windows SDK 函数 **OutputDebugStringA** 将以 null 结尾的字节字符串写入活动调试程序的框架库函数。 如果应用程序没有调试器，则系统调试程序将显示字符串。 如果应用程序没有调试器并且系统调试程序不活动， **则 debugPrintf 不** 执行任何操作。 
  
此函数不返回值。
  
```cs
void WINAPI debugPrintf(LPSTR lpFormat, arguments);
```

## <a name="parameters"></a>参数

 _lpFormat (LPSTR)_
  
格式字符串，遵循用于 **sprintf** 函数的语法和规则。 
  
 _arguments_
  
匹配格式字符串的零个或多个参数。
  
## <a name="example"></a>示例

此函数打印一个字符串，以显示控件已传递给它。 编译_DEBUG必须定义该标志，否则此函数不执行任何操作。
  
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

