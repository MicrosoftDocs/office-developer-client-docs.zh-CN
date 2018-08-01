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
ms.openlocfilehash: 4ea77023bdc9442325f4af46d23c107e7172ceaf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778789"
---
# <a name="sizeddtbledit"></a>SizedDtblEdit

**适用于**： Outlook 
  
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
    
## <a name="remarks"></a>说明

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

