---
title: SizedDtblLabel
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblLabel
api_type:
- COM
ms.assetid: c7cb8cf9-7abd-4ee3-b88c-d61695f4ed31
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c2e275e373677e50510a0aa87f5060070a870a0f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778806"
---
# <a name="sizeddtbllabel"></a>SizedDtblLabel

**适用于**： Outlook 
  
创建一个名为的结构包含用于描述 label 控件和指定长度的关联的标签[DTBLLABEL](dtbllabel.md)结构。 
  
|||
|:-----|:-----|
|头文件中指定：  <br/> |Mapidefs.h  <br/> |
|相关的结构  <br/> |**DTBLLABEL** <br/> |
   
```cpp
SizedDtblLabel (n, u)
```

## <a name="parameters"></a>参数

_n_
  
> 标签的长度。 这包括结束 NULL 字符。 
    
_u_
  
> 新结构的的名称。
    
## <a name="remarks"></a>说明

**SizedDtblLabel**宏允许您定义显示表标签时已知的标签中的字符数。 使用下列成员来创建新的结构： 
  
```cpp
DTBLLABEL dtbllabel;
TCHAR lpszLabelName[n];
```

若要将指针生成结构从**SizedDtblLabel**宏作为**DTBLLABEL**结构指针，执行以下的强制转换： 
  
```cpp
lpDtblLabel = (LPDTBLLABEL) &SizedDtblLabel;
```

## <a name="see-also"></a>另请参阅

- [DTBLLABEL](dtbllabel.md)
- [与结构相关的宏](macros-related-to-structures.md)

