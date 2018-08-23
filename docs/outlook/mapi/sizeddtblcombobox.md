---
title: SizedDtblComboBox
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblComboBox
api_type:
- COM
ms.assetid: 1e5ea9f2-1029-4584-845a-890d3e956036
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 39854c320078d2e2ca2365244f094e28962380d0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593653"
---
# <a name="sizeddtblcombobox"></a>SizedDtblComboBox
 
**适用于**： Outlook 2013 |Outlook 2016 
  
创建一个名为的结构包含用于描述组合框控件和最大可以关联的编辑控件中输入的字符数[DTBLCOMBOBOX](dtblcombobox.md)结构。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**DTBLCOMBOBOX** <br/> |
   
```cpp
SizedDtblComboBox (n, u)
```

## <a name="parameters"></a>参数

_n_
  
> 可以在组合框中输入的字符数编辑控件。 
    
_u_
  
> 新结构的的名称。
    
## <a name="remarks"></a>注解

**SizedDtblComboBox**宏允许您定义组合框时已知启用的字符串的长度。 使用下列成员来创建新的结构： 
  
```cpp
DTBLCOMBOBOX dtblcombobox;
TCHAR lpszCharsAllowed[n];

```

若要将指针生成结构从**SizedDtblComboBox**宏作为**DTBLCOMBOBOX**结构指针，执行以下的强制转换： 
  
```cpp
lpDtblComboBox = (LPDTBLCOMBOBOX) &SizedDtblComboBox;

```

## <a name="see-also"></a>另请参阅

- [DTBLCOMBOBOX](dtblcombobox.md)
- [与结构相关的宏](macros-related-to-structures.md)

