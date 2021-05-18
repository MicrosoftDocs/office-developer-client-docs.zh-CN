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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 6d063213e3f83451e8a072e71f0878174214f73e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412462"
---
# <a name="xlgetbinaryname"></a>xlGetBinaryName

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用于返回由 [xlDefineBinaryName 函数保存的数据的句柄](xldefinebinaryname.md)。 具有定义的二进制名称的数据随工作簿一起保存，并且随时都可以按名称访问。 有关详细信息，请参阅 XLL 开发中的已知问题中的"二Excel[范围限制"。](known-issues-in-excel-xll-development.md)
  
```cs
Excel12(xlGetBinaryName, LPXLOPER12 pxRes, 1, LPXLOPER12 pxName);
```

## <a name="parameters"></a>参数

_pxRes_ (**xltypeBigData** 或 **xltypeErr**) 
  
指定检索到的数据的 Bigdata 结构或错误是无法检索数据或者未定义名称。 函数返回时 **，XLOPER**  /  **XLOPER12** 的 hdata 成员包含命名数据的句柄。  当不再需要 **xlFree 时，应在调用 xlFree** 时释放 _pxRes。_ 
  
_pxName_ (**xltypeStr**) 
  
指定数据名称的字符串。
  
## <a name="remarks"></a>备注

Microsoft Excel **hdata** 中返回的内存句柄。 在Windows中，句柄是由 **GlobalAlloc** 函数 (分配的全局内存) 。 
  
## <a name="see-also"></a>另请参阅

- [xlDefineBinaryName](xldefinebinaryname.md)
- [只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

