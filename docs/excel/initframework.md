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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 2d7e3286d794d6f21da9ef83ca44d18ec242c063
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773748"
---
# <a name="initframework"></a>InitFramework

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
初始化 Framework 库中，只需初始化临时**XLOPER**的框架库函数/ **XLOPER12**内存数据结构，释放任何已分配的内存。 
  
```cs
short WINAPI InitFramework(void);
```

## <a name="parameters"></a>参数

此函数不采用任何参数。
  
## <a name="return-value"></a>返回值

此函数不返回值。
  
## <a name="example"></a>示例

本示例使用**InitFramework**函数释放所有临时内存。 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI InitFrameworkExample(void)
{
    InitFramework();
    return 1;
}
```

## <a name="see-also"></a>另请参阅



[Framework 库中的函数](functions-in-the-framework-library.md)

