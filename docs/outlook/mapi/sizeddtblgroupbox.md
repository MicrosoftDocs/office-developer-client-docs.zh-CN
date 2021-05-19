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
ms.openlocfilehash: 0a9bda8831f4a38b62d71a54115c40bb3374d97d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419315"
---
# <a name="sizeddtblgroupbox"></a>SizedDtblGroupBox

**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个命名结构，其中包含用于描述分组框控件和指定长度的标签的 [DTBLGROUPBOX](dtblgroupbox.md) 结构。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关结构：  <br/> |**DTBLGROUPBOX** <br/> |
   
```cpp
SizedDtblGroupBox (n, u)
```

## <a name="parameters"></a>参数

_n_
  
> 分组框标签的长度。 
    
_u_
  
> 新结构的名称。
    
## <a name="remarks"></a>备注

**SizedDtblGroupBox** 宏允许你在标签长度已知时定义分组框控件。 新结构由以下成员创建： 
  
```cpp
DTBLGROUPBOX dtblgroupbox;
TCHAR lpszLabel[n];

```

若要将指向 **SizedDtblGroupBox** 宏生成的结构的指针用作 **DTBLGROUPBOX** 结构指针，请执行以下转换： 
  
```cpp
lpDtblGroupBox = (LPDTBLGROUPBOX) &SizedDtblGroupBox;

```

## <a name="see-also"></a>另请参阅

- [DTBLGROUPBOX](dtblgroupbox.md)
- [与结构相关的宏](macros-related-to-structures.md)

