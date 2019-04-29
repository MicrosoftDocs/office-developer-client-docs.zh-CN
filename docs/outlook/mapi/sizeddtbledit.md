---
title: SizedDtblEdit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblEdit
api_type:
- COM
ms.assetid: a658d027-03a2-4cde-bf99-563e8521cb31
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b5b9c42d944ad9d3ce92e99d08d29964944c8028
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437642"
---
# <a name="sizeddtbledit"></a>SizedDtblEdit

**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个命名的结构, 其中包含用于描述编辑控件的[DTBLEDIT](dtbledit.md)结构, 以及可以在控件中输入的最大字符数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |**DTBLEDIT** <br/> |
   
```cpp
SizedDtblEdit (n, u)
```

## <a name="parameters"></a>参数

_n_
  
> 可以在编辑控件中输入的最大字符数。
    
_u_
  
> 新结构的名称。
    
## <a name="remarks"></a>说明

**SizedDtblEdit**宏允许您在已知启用的字符数时定义编辑控件。 新结构是使用以下成员创建的: 
  
```cpp
DTBLEDIT dtbledit;
TCHAR lpszCharsAllowed[n];

```

若要将指向**SizedDtblEdit**宏的结果结构的指针用作**DTBLEDIT**结构指针, 请执行以下转换: 
  
```cpp
lpDtblEdit = (LPDTBLEDIT) &SizedDtblEdit;

```

## <a name="see-also"></a>另请参阅

- [DTBLEDIT](dtbledit.md)
- [与结构相关的宏](macros-related-to-structures.md)

