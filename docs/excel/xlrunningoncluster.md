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
ms.openlocfilehash: f5c630c73899b07e2727a7d42b18eb1891797bab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310099"
---
# <a name="xlrunningoncluster"></a>xlRunningOnCluster

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
返回一个值, 该值指示用户定义的函数是否在群集上运行。 
  
```cpp
Excel12(xlRunningOnCluster, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a>参数

此函数没有参数。
  
## <a name="return-value"></a>返回值

如果函数在 Excel 进程中运行, 则在**xlTypeInt**类型的**XLOPER12**中返回0。 如果该函数在群集上运行, 则返回类型和值由群集连接器提供程序确定。
  
## <a name="requirements"></a>Requirements

此函数是在 xlcall.h 头文件中定义的。
  
## <a name="see-also"></a>另请参阅

- [群集安全函数](cluster-safe-functions.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

