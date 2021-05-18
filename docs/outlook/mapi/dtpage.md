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
ms.openlocfilehash: ad8aec8d015849965bea6ac011c8a45e75c69ca1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408220"
---
# <a name="dtpage"></a>DTPAGE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述由 [BuildDisplayTable](builddisplaytable.md) 函数从显示表构建的对话框。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> **lpctl** 成员指向的控件计数。 
    
 **lpszResourceName**
  
> 指向对话框资源的名称或整数标识符的指针。 
    
 **lpszComponent**
  
> 指向出现在 MAPISVC.INF **中的 [帮助文件映射]** 部分中的字符串的指针。 由于 **lpszComponent** 与 **ulItemID** 成员联合，因此只有其中一个成员具有有效数据。 
    
 **ulItemID**
  
> 整数资源标识符，其值小于或等于 65535，可以从中读取帮助文件名。 由于 **ulItemID** 与 **lpszComponent** 成员联合在一起，因此只有其中一个成员具有有效数据。 
    
 **lpctl**
  
> 指向 [DTCTL](dtctl.md) 结构的数组的指针，页面上每个控件一个。 
    
## <a name="remarks"></a>备注

若要标识选项卡式页面的帮助文件，将 **lpszComponent** 成员设置为硬编码字符串或 **ulItemID** 成员设置为整数资源标识符。 
  
MAPISVC **中 [帮助文件映射]** 部分的每个条目。INF 由左侧的组件字符串（不超过 30 个字符）和右侧帮助文件路径组成。 **ulItemID 和** **lpszResourceName** 都位于 **BuildDisplayTable** 的 _hInstance_ 参数中。 有关详细信息，请参阅 [MAPISVC。INF [Help File Mappings] Section](mapisvc-inf-help-file-mappings-section.md).
  
尽管 **BuildDisplayTable** 使用此结构从控件资源构建显示表，但 **DTPAGE** 结构永远不会显示在显示表本身中。 
  
有关显示表的概述，请参阅显示 [表](display-tables.md)。 若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[BuildDisplayTable](builddisplaytable.md)
  
[DTBLPAGE](dtblpage.md)
  
[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

