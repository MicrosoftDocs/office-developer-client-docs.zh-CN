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
ms.openlocfilehash: 7e50589b52f3e99bf2569a55bb7d3ca4f8247fd6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591658"
---
# <a name="sizeddtbledit"></a>SizedDtblEdit

**适用于**： Outlook 2013 |Outlook 2016 
  
创建一个名为的结构包含用于描述编辑控件和最大可以在控件中输入的字符数[DTBLEDIT](dtbledit.md)结构。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**DTBLEDIT** <br/> |
   
```cpp
SizedDtblEdit (n, u)
```

## <a name="parameters"></a>参数

_n_
  
> 最大可编辑控件中输入的字符数。
    
_u_
  
> 新结构的的名称。
    
## <a name="remarks"></a>注解

**SizedDtblEdit**宏允许您定义的编辑控件时已知的已启用的字符数。 使用下列成员来创建新的结构： 
  
```cpp
DTBLEDIT dtbledit;
TCHAR lpszCharsAllowed[n];

```

若要将指针生成结构从**SizedDtblEdit**宏作为**DTBLEDIT**结构指针，执行以下的强制转换： 
  
```cpp
lpDtblEdit = (LPDTBLEDIT) &SizedDtblEdit;

```

## <a name="see-also"></a>另请参阅

- [DTBLEDIT](dtbledit.md)
- [与结构相关的宏](macros-related-to-structures.md)

