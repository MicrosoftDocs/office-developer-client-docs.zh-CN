---
title: DTBLGROUPBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLGROUPBOX
api_type:
- COM
ms.assetid: 5e444b62-d6b6-4cfc-8601-d34aa004c1e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 324cfe9d7c412b3bb0e3150b8eec51aaeb6a0e93
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438391"
---
# <a name="dtblgroupbox"></a>DTBLGROUPBOX

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述将在基于显示表构建的对话框中使用的组框控件。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[SizedDtblGroupBox](sizeddtblgroupbox.md) <br/> |
   
```cpp
typedef struct _DTBLGROUPBOX
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
} DTBLGROUPBOX, FAR *LPDTBLGROUPBOX;

```

## <a name="members"></a>Members

 **ulbLpszLabel**
  
> 在分组框随附的字符串内存中的位置。 如果显示，则标签显示在框的左侧顶部。
    
 **ulFlags**
  
> 用于指定 **ulbLpszLabel** 成员指向的标签格式的标志的位掩码。 可以设置以下标志： 
    
MAPI_UNICODE 
  
> 标签采用 Unicode 格式。 如果未MAPI_UNICODE，则标签采用 ANSI 格式。
    
## <a name="remarks"></a>备注

**DTBLGROUPBOX** 结构描述用于直观关联对话框中其他控件的分组框控件。 突出显示技术涉及用一个框包围其他控件。 
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

