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
ms.openlocfilehash: 1ae675d1d4adf841e18bbfc8990913136afe8b4b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408612"
---
# <a name="sizeddtbllabel"></a>SizedDtblLabel

**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个命名的结构, 其中包含用于描述标签控件和指定长度的关联标签的[DTBLLABEL](dtbllabel.md)结构。 
  
|||
|:-----|:-----|
|在头文件中指定:  <br/> |mapidefs。h  <br/> |
|相关结构  <br/> |**DTBLLABEL** <br/> |
   
```cpp
SizedDtblLabel (n, u)
```

## <a name="parameters"></a>参数

_n_
  
> 标签的长度。 这包括结尾的 NULL 字符。 
    
_u_
  
> 新结构的名称。
    
## <a name="remarks"></a>说明

**SizedDtblLabel**宏允许您在标签中的字符数已知时定义显示表标签。 新结构是使用以下成员创建的: 
  
```cpp
DTBLLABEL dtbllabel;
TCHAR lpszLabelName[n];
```

若要将指向**SizedDtblLabel**宏的结果结构的指针用作**DTBLLABEL**结构指针, 请执行以下转换: 
  
```cpp
lpDtblLabel = (LPDTBLLABEL) &SizedDtblLabel;
```

## <a name="see-also"></a>另请参阅

- [DTBLLABEL](dtbllabel.md)
- [与结构相关的宏](macros-related-to-structures.md)

