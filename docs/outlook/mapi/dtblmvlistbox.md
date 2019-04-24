---
title: DTBLMVLISTBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLMVLISTBOX
api_type:
- COM
ms.assetid: 1c22f842-d0e7-44f0-a7d5-c9c2aa6b8820
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ae8f3ab28837bf0579549ead46c28477f815f35c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338274"
---
# <a name="dtblmvlistbox"></a>DTBLMVLISTBOX

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述将在从显示表生成的对话框中显示的多值列表。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _DTBLMVLISTBOX
{
  ULONG ulFlags;
  ULONG ulMVPropTag;
} DTBLMVLISTBOX, FAR * LPDTBLMVLISTBOX;

```

## <a name="members"></a>成员

 **ulFlags**
  
> 保留必须为零。
    
 **ulMVPropTag**
  
> 类型为 PT_MV_TSTRING 的多值属性的属性标记。
    
## <a name="remarks"></a>注解

**DTBLMVLISTBOX**结构描述具有项的只读列表的标准多值列表。 通过使用标准的多值列表, 这些值会立即显示出来。 
  
显示的数据来自**ulMVPropTag**成员中标识的属性。 不需要从与显示表相关联的属性接口中进行读取。 此外, 因为用户无法从这些类型的列表中进行选择, 所以不会将数据写入属性接口。 
  
多值列表仅支持多值字符串属性;不支持其他多值属性类型。 
  
有关显示表的概述, 请参阅[显示表](display-tables.md)。 有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

