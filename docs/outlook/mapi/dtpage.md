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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287103"
---
# <a name="dtpage"></a>DTPAGE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍了通过[BuildDisplayTable](builddisplaytable.md)函数从显示表生成的对话框。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
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
  
> 由**lpctl**成员指向的控件的计数。 
    
 **lpszResourceName**
  
> 指向对话框资源的名称或整数标识符的指针。 
    
 **lpszComponent**
  
> 指向 mapisvc.inf 中的 **[帮助文件映射]** 部分中显示的字符串的指针。 由于**lpszComponent**与**ulItemID**成员联合在联合中, 因此只有其中一个成员具有有效数据。 
    
 **ulItemID**
  
> 值小于或等于65535的整数资源标识符, 可从该标识符读取帮助文件名。 由于**ulItemID**与**lpszComponent**成员联合在联合中, 因此只有其中一个成员具有有效数据。 
    
 **lpctl**
  
> 指向[DTCTL](dtctl.md)结构的数组的指针, 页面上的每个控件对应一个。 
    
## <a name="remarks"></a>注解

若要确定选项卡式页面的帮助文件, 请将**lpszComponent**成员设置为硬编码字符串或将**ulItemID**成员设置为整数资源标识符。 
  
mapisvc.inf 中的 **[帮助文件映射]** 部分中的每个条目。INF 包含一个组件字符串, 不超过30个字符, 位于右侧的左侧和帮助文件路径中。 在**BuildDisplayTable**的_hInstance_参数中都找到**ulItemID**和**lpszResourceName** 。 有关详细信息, 请参阅[mapisvc.inf。INF [帮助文件映射] 部分](mapisvc-inf-help-file-mappings-section.md)。
  
虽然**BuildDisplayTable**使用此结构从控件资源生成显示表, 但**DTPAGE**结构从不显示在显示表本身中。 
  
有关显示表的概述, 请参阅[显示表](display-tables.md)。 有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[BuildDisplayTable](builddisplaytable.md)
  
[DTBLPAGE](dtblpage.md)
  
[DTCTL](dtctl.md)


[MAPI 结构](mapi-structures.md)

