---
title: DTBLMVDDLBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLMVDDLBOX
api_type:
- COM
ms.assetid: 0e6283dc-9a08-460f-9400-03f0ceb4081c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 33b4fd87f33c26db15e1a6a28f077c393168db91
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420743"
---
# <a name="dtblmvddlbox"></a>DTBLMVDDLBOX

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述将在从显示表构建的对话框中使用的下拉列表。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _DTBLMVDDLBX
{
  ULONG ulFlags;
  ULONG ulMVPropTag;
} DTBLMVDDLBX, FAR * LPDTBLMVDDLBX;

```

## <a name="members"></a>成员

 **ulFlags**
  
> 保留;必须为零。
    
 **ulMVPropTag**
  
> 类型为 PT_MV_TSTRING 的多值属性的属性标记。 此属性的值在下拉列表中显示为不同的条目。
    
## <a name="remarks"></a>备注

**DTBLMVDDLBOX** 结构描述多值下拉列表（只读项目列表）。 通过使用多值下拉列表，当用户单击滚动条时将显示值。 
  
显示的数据来自 **ulMVPropTag** 成员中标识的属性。 不需要从与显示表关联的属性接口读取。 此外，由于用户无法从这些类型的列表框中进行选择，因此不会将数据写入属性接口。 
  
多值下拉列表仅支持多值字符串属性;不支持其他多值属性类型。 
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

