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
ms.openlocfilehash: f7c1241f2ad31dee8277f3b3b77ac02137067a12
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576307"
---
# <a name="dtblmvlistbox"></a>DTBLMVLISTBOX

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述将显示表中生成的对话框中显示多值的列表。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _DTBLMVLISTBOX
{
  ULONG ulFlags;
  ULONG ulMVPropTag;
} DTBLMVLISTBOX, FAR * LPDTBLMVLISTBOX;

```

## <a name="members"></a>Members

 **ulFlags**
  
> 保留;必须为零。
    
 **ulMVPropTag**
  
> 属性标记类型 PT_MV_TSTRING 的多值属性。
    
## <a name="remarks"></a>注解

**DTBLMVLISTBOX**结构介绍具有只读的项目列表的标准多值的列表。 通过使用标准的多值的列表，立即显示的值。 
  
显示的数据来自**ulMVPropTag**成员中标识的属性。 没有任何要求读取与显示表相关联的属性接口。 另外，由于用户未能够在这些类型的列表中进行选择，因此是不将数据写入属性界面。 
  
多值列表中; 支持仅多值的字符串属性不支持其他多值的属性类型。 
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

