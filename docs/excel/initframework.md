---
title: InitFramework
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- InitFramework
keywords:
- initframework 函数 [excel 2007]
localization_priority: Normal
ms.assetid: c472a14a-92a6-46f6-924c-db8d6199d6fb
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 34fe8f4a606956b90a0d005b0bc523cea460153f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420751"
---
# <a name="initframework"></a>InitFramework

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
初始化框架库的框架库函数，该函数仅初始化临时 **XLOPER** /  **XLOPER12** 内存数据结构，从而释放已分配的任何内存。 
  
```cs
short WINAPI InitFramework(void);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="return-value"></a>返回值

此函数不返回值。
  
## <a name="example"></a>示例

此示例使用 **InitFramework** 函数释放所有临时内存。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI InitFrameworkExample(void)
{
    InitFramework();
    return 1;
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

