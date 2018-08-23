---
title: DTPAGE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTPAGE
api_type:
- COM
ms.assetid: 500f60ed-fdec-4d70-8cf5-664c46643956
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 769ae984e4b6e8610ca7909ea2ac714d9d04d698
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589670"
---
# <a name="dtpage"></a>DTPAGE

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
介绍器构建[BuildDisplayTable](builddisplaytable.md)函数显示表中的对话框。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct DTPAGE
{
  ULONG cctl;
  LPSTR lpszResourceName;
  union
  {
    LPSTR lpszComponent;
    ULONG ulItemID;
  }
  LPDTCTL lpctl;
} DTPAGE, FAR *LPDTPAGE;

```

## <a name="members"></a>Members

 **cctl**
  
> 控件所指的**lpctl**成员数。 
    
 **lpszResourceName**
  
> 指向对话框资源的名称或整数标识符。 
    
 **lpszComponent**
  
> 指向在 MAPISVC.INF 的 **[帮助文件映射]** 节中显示的字符串。 因为**lpszComponent**正在**ulItemID**成员具有的联合，这些成员之一具有有效的数据。 
    
 **ulItemID**
  
> 整数资源标识符的值小于或等于到 65535 可以从中读取的帮助文件名称。 因为**ulItemID**正在**lpszComponent**成员具有的联合，这些成员之一具有有效的数据。 
    
 **lpctl**
  
> 指向[DTCTL](dtctl.md)结构，一个用于该页面上的每个控件数组的指针。 
    
## <a name="remarks"></a>注解

若要确定选项卡式页面的帮助文件，设置为整数资源标识符的硬编码的字符串的**lpszComponent**成员或**ulItemID**成员。 
  
在 MAPISVC **[帮助文件映射]** 节中每个项。INF 包含组件字符串，不得多于 30 个字符，在左侧和右侧的帮助文件路径。 **UlItemID**和**lpszResourceName** **BuildDisplayTable**的_hInstance_参数中找到。 有关详细信息，请参阅[MAPISVC。INF [帮助文件映射] 部分](mapisvc-inf-help-file-mappings-section.md)。
  
尽管**BuildDisplayTable**使用此结构来构建控件资源中的显示表中显示表本身永远不会显示**DTPAGE**结构。 
  
显示表的概述，请参阅[显示表](display-tables.md)。 有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[BuildDisplayTable](builddisplaytable.md)
  
[DTBLPAGE](dtblpage.md)
  
[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

