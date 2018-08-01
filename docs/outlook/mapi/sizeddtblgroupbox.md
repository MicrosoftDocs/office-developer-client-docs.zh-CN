---
title: SizedDtblGroupBox
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblGroupBox
api_type:
- COM
ms.assetid: 7ca01bf7-5185-41cc-907e-01f256345997
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a3d8a76905aa9abb0e5bf001688608e03446704a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778797"
---
# <a name="sizeddtblgroupbox"></a>SizedDtblGroupBox

**适用于**： Outlook 
  
创建一个名为的结构包含用于描述组框控件和一个指定长度的标签[DTBLGROUPBOX](dtblgroupbox.md)结构。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**DTBLGROUPBOX** <br/> |
   
```cpp
SizedDtblGroupBox (n, u)
```

## <a name="parameters"></a>参数

_n_
  
> 组框标签的长度。 
    
_u_
  
> 新结构的的名称。
    
## <a name="remarks"></a>说明

**SizedDtblGroupBox**宏允许您定义一个组框控件时已知标签的长度。 使用下列成员来创建新的结构： 
  
```cpp
DTBLGROUPBOX dtblgroupbox;
TCHAR lpszLabel[n];

```

若要将指针生成结构从**SizedDtblGroupBox**宏作为**DTBLGROUPBOX**结构指针，执行以下的强制转换： 
  
```cpp
lpDtblGroupBox = (LPDTBLGROUPBOX) &SizedDtblGroupBox;

```

## <a name="see-also"></a>另请参阅

- [DTBLGROUPBOX](dtblgroupbox.md)
- [与结构相关的宏](macros-related-to-structures.md)

