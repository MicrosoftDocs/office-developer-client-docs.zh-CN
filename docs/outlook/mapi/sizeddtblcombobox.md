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
ms.openlocfilehash: 8861c8f86eaab6defb270b673e0ee200446aedb3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416263"
---
# <a name="sizeddtblcombobox"></a>SizedDtblComboBox
 
**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个命名的结构, 其中包含用于描述组合框控件的[DTBLCOMBOBOX](dtblcombobox.md)结构, 以及可在关联的编辑控件中输入的最大字符数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关结构:  <br/> |**DTBLCOMBOBOX** <br/> |
   
```cpp
SizedDtblComboBox (n, u)
```

## <a name="parameters"></a>参数

_n_
  
> 可在组合框的编辑控件中输入的字符数。 
    
_u_
  
> 新结构的名称。
    
## <a name="remarks"></a>说明

**SizedDtblComboBox**宏允许您在已知启用的字符字符串的长度时定义组合框。 新结构是使用以下成员创建的: 
  
```cpp
DTBLCOMBOBOX dtblcombobox;
TCHAR lpszCharsAllowed[n];

```

若要将指向**SizedDtblComboBox**宏的结果结构的指针用作**DTBLCOMBOBOX**结构指针, 请执行以下转换: 
  
```cpp
lpDtblComboBox = (LPDTBLCOMBOBOX) &SizedDtblComboBox;

```

## <a name="see-also"></a>另请参阅

- [DTBLCOMBOBOX](dtblcombobox.md)
- [与结构相关的宏](macros-related-to-structures.md)

