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
ms.openlocfilehash: ef38893c9ad44556cc9220809b5e407f86fd2642
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576314"
---
# <a name="dtblgroupbox"></a>DTBLGROUPBOX

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
描述将显示表中生成的对话框中使用的分组框控件。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[SizedDtblGroupBox](sizeddtblgroupbox.md) <br/> |
   
```cpp
typedef struct _DTBLGROUPBOX
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
} DTBLGROUPBOX, FAR *LPDTBLGROUPBOX;

```

## <a name="members"></a>Members

 **ulbLpszLabel**
  
> 在字符串附带组框的内存中的位置。 如果显示，标签显示在框中的顶部、 左上方。
    
 **ulFlags**
  
> 用于指定所指的**ulbLpszLabel**成员标签的格式的标志位掩码。 可以设置以下标记： 
    
MAPI_UNICODE 
  
> 标签为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。
    
## <a name="remarks"></a>注解

**DTBLGROUPBOX**结构介绍用于直观地将在对话框中的其他控件相关联的分组框控件。 突出显示的项技术涉及周围的框中的其他控件。 
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

