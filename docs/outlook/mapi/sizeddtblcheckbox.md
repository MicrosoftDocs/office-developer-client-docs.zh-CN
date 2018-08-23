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
ms.openlocfilehash: 6120439ea0d98ed6b64fe1542a4372265574723a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567529"
---
# <a name="sizeddtblcheckbox"></a>SizedDtblCheckBox
 
**适用于**： Outlook 2013 |Outlook 2016 
  
创建一个名为的结构包含用于描述复选框控件和一个指定长度的标签[DTBLCHECKBOX](dtblcheckbox.md)结构。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**DTBLCHECKBOX** <br/> |
   
```cpp
SizedDtblCheckBox (n, u)
```

## <a name="parameters"></a>参数

_n_
  
> 标签的新结构中包含的长度。
    
_u_
  
> 新结构的的名称。
    
## <a name="remarks"></a>注解

**SizedDtblCheckBox**宏可以定义一个复选框，当已知的标签字符数。 使用下列成员来创建新的结构： 
  
```cpp
DTBLCHECKBOX dtblcheckbox;
TCHAR lpszLabel[n];
```

若要将指针生成结构从**SizedDtblCheckBox**宏作为**DTBLCHECKBOX**结构指针，执行以下的强制转换： 
  
```cpp
lpDtblCheckBox = (LPDTBLCHECKBOX) &SizedDtblCheckBox;
```

## <a name="see-also"></a>另请参阅

- [DTBLCHECKBOX](dtblcheckbox.md)
- [与结构相关的宏](macros-related-to-structures.md)

