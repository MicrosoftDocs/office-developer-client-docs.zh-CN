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
ms.openlocfilehash: d2332967e798b43a350c0733cd7398e2a921add6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773847"
---
# <a name="xlgetbinaryname"></a>xlGetBinaryName

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于返回[xlDefineBinaryName 函数](xldefinebinaryname.md)保存数据的句柄。 数据定义二进制文件名称保存在工作薄和随时都可以通过名称访问。 有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中的"二进制命名范围限制"。
  
```cs
Excel12(xlGetBinaryName, LPXLOPER12 pxRes, 1, LPXLOPER12 pxName);
```

## <a name="parameters"></a>参数

_pxRes_（**xltypeBigData**或**xltypeErr**）
  
无法检索 Bigdata 结构指定检索到的数据或错误数据或未定义名称。 当函数返回时， **XLOPER**的**hdata**成员/ **XLOPER12**包含已命名的数据的句柄。  _pxRes_应释放**xlFree**当不再需要时将调用。 
  
_pxName_(**xltypeStr**)
  
指定的数据的名称的字符串。
  
## <a name="remarks"></a>说明

Microsoft Excel 拥有**hdata**中返回的内存句柄。 在 Windows 中，句柄是 （分配**GlobalAlloc**函数） 的全局内存句柄。 
  
## <a name="see-also"></a>另请参阅

- [xlDefineBinaryName](xldefinebinaryname.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

