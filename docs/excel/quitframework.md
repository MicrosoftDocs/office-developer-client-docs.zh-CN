---
title: QuitFramework
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- QuitFramework
keywords:
- quitframework 函数
localization_priority: Normal
ms.assetid: d17a3efe-c278-4ef1-b8f9-b958ae012361
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9408a7938927214802935e54ec8e53b1469e5016
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408570"
---
# <a name="quitframework"></a>QuitFramework

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
framework library 函数, 它 uninitializes 框架库, 该函数简单地重新初始化临时**XLOPER**/ **XLOPER12**内存数据结构, 从而释放已分配的所有内存。 
  
```cs
short WINAPI QuitFramework(void);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数不返回值。
  
## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

