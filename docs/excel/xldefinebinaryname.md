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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 14515cc262ea398a9f200c0de3a1f6b64c758b3d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773831"
---
# <a name="xldefinebinaryname"></a>xlDefineBinaryName

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于分配**xltypeBigData** **XLOPER**永久存储/ **XLOPER12**。 数据定义二进制文件名称与工作簿，保存并随时都可以通过名称访问。 有关详细信息，请参阅"二进制名称范围限制" [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中。
  
```cs
Excel12(xlDefineBinaryName, 0, 2, LPXLOPER12 pxName, LPXLOPER12 pxData);
```

## <a name="parameters"></a>参数

 _pxName_(**xltypeStr**)
  
指定的数据的名称的字符串。 该字符串是受到相同命名为已定义的名称的限制。
  
 _pxData_(**xltypeBigData**)
  
Bigdata 结构，它指定要存储的数据。 当您调用此函数时， **bigdata**结构的**lpbData**成员应指向为其正在定义名称，数据和**cbData**成员应包含以字节为单位的数据的长度。 
  
如果_pxData_参数不是指定 (**xltypeMissing**)，将删除由_pxName_指定的命名的分配。 
  
## <a name="see-also"></a>另请参阅



[xlGetBinaryName](xlgetbinaryname.md)


[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[Excel XLL 开发中的已知的问题](known-issues-in-excel-xll-development.md)

