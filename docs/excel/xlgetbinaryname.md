---
title: xlGetBinaryName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlGetBinaryName
keywords:
- xlgetbinaryname 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 66af3f78-65b5-42e0-82f9-ffd639d41751
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 6d063213e3f83451e8a072e71f0878174214f73e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303834"
---
# <a name="xlgetbinaryname"></a>xlGetBinaryName

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于返回[xlDefineBinaryName 函数](xldefinebinaryname.md)所保存数据的句柄。 带有定义的二进制名称的数据将与工作簿一起保存, 并可在任何时候通过名称访问。 有关详细信息, 请参阅[Excel XLL 开发的已知问题](known-issues-in-excel-xll-development.md)中的 "二进制名称作用域限制"。
  
```cs
Excel12(xlGetBinaryName, LPXLOPER12 pxRes, 1, LPXLOPER12 pxName);
```

## <a name="parameters"></a>参数

_pxRes_(**xltypeBigData**或**xltypeErr**)
  
Bigdata 结构指定检索的数据或错误是无法检索数据, 或者未定义名称。 当函数返回时, **XLOPER**/ **XLOPER12**的**hdata**成员包含已命名数据的句柄。  当不再需要时, 应在对**xlFree**的调用中释放_pxRes_ 。 
  
_pxName_(**xltypeStr**)
  
一个指定数据的名称的字符串。
  
## <a name="remarks"></a>注解

Microsoft Excel 拥有在**hdata**中返回的内存句柄。 在 Windows 中, 句柄是全局内存句柄 (由**GlobalAlloc**函数分配)。 
  
## <a name="see-also"></a>另请参阅

- [xlDefineBinaryName](xldefinebinaryname.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

