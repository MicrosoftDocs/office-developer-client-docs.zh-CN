---
title: SizedDtblCheckBox
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblCheckBox
api_type:
- COM
ms.assetid: 9d04a124-54d4-43ac-967f-ea8e7a09b1d0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6d23d56a27095497aedc64d7bbf5ffda266d0c97
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420806"
---
# <a name="sizeddtblcheckbox"></a>SizedDtblCheckBox
 
**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个命名的结构, 其中包含用于描述复选框控件和标签指定长度的[DTBLCHECKBOX](dtblcheckbox.md)结构。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |**DTBLCHECKBOX** <br/> |
   
```cpp
SizedDtblCheckBox (n, u)
```

## <a name="parameters"></a>参数

_n_
  
> 要包含在新结构中的标签的长度。
    
_u_
  
> 新结构的名称。
    
## <a name="remarks"></a>说明

**SizedDtblCheckBox**宏允许您在标签字符的数目已知时定义复选框。 新结构是使用以下成员创建的: 
  
```cpp
DTBLCHECKBOX dtblcheckbox;
TCHAR lpszLabel[n];
```

若要将指向**SizedDtblCheckBox**宏的结果结构的指针用作**DTBLCHECKBOX**结构指针, 请执行以下转换: 
  
```cpp
lpDtblCheckBox = (LPDTBLCHECKBOX) &SizedDtblCheckBox;
```

## <a name="see-also"></a>另请参阅

- [DTBLCHECKBOX](dtblcheckbox.md)
- [与结构相关的宏](macros-related-to-structures.md)

