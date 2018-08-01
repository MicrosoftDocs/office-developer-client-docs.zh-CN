---
title: xlRunningOnCluster
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
keywords:
- xlrunningoncluster
localization_priority: Normal
ms.assetid: 7662f255-4184-4af0-97f5-9a89347a201a
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f42ccbeb94e1fc6b6cf880f1b32ee1bfeb24997e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773878"
---
# <a name="xlrunningoncluster"></a>xlRunningOnCluster

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
返回一个值，该值指示是否在群集上运行的用户定义的函数。 
  
```cpp
Excel12(xlRunningOnCluster, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a>参数

此函数具有任何参数。
  
## <a name="return-value"></a>返回值

如果在函数 Excel 进程中运行，在类型**xlTypeInt** **XLOPER12**返回 0。 如果在函数在群集上运行，由群集连接器提供程序确定的返回类型和值。
  
## <a name="requirements"></a>要求

Xlcall.h 头文件中定义此函数。
  
## <a name="see-also"></a>另请参阅

- [群集安全函数](cluster-safe-functions.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

