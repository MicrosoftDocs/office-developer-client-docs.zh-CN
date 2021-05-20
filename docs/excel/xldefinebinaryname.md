---
title: xlDefineBinaryName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlDefineBinaryName
keywords:
- xldefinebinaryname 函数 [excel 2007]
localization_priority: Normal
ms.assetid: e3e8f91b-cc31-4f09-9941-f950ae96820a
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3c7fc4f6b6fc7179c1ca84043895273b2781f8b5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430250"
---
# <a name="xldefinebinaryname"></a>xlDefineBinaryName

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
用于为 **xltypeBigData** **XLOPER** /  **XLOPER12 分配永久性存储**。 具有定义的二进制名称的数据随工作簿一起保存，并且随时都可以按名称访问。 有关详细信息，请参阅 XLL 开发中的已知问题中的"二Excel[范围限制"。](known-issues-in-excel-xll-development.md)
  
```cs
Excel12(xlDefineBinaryName, 0, 2, LPXLOPER12 pxName, LPXLOPER12 pxData);
```

## <a name="parameters"></a>参数

 _pxName_ (**xltypeStr**) 
  
指定数据名称的字符串。 字符串受与已定义名称相同的命名限制约束。
  
 _pxData_ (**xltypeBigData**) 
  
用于指定要存储数据的 Bigdata 结构。 调用此函数时 **，bigdata** 结构的 **lpbData** 成员应指向要定义其名称的数据 **，cbData** 成员应包含数据的长度（以字节为单位）。 
  
如果在 **xltypeMissing** (未指定 _pxData_ 参数) _pxName_ 指定的已命名分配将被删除。 
  
## <a name="see-also"></a>另请参阅



[xlGetBinaryName](xlgetbinaryname.md)


[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[XLL Excel中的已知问题](known-issues-in-excel-xll-development.md)

