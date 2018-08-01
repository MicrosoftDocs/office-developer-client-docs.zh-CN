---
title: SizedDtblPage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblPage
api_type:
- COM
ms.assetid: 47b2a69d-e902-429f-8b31-166b51aeaf7f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a1530443600df7cb73ff27d5cfbeab46f81bc53c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778792"
---
# <a name="sizeddtblpage"></a>SizedDtblPage

**适用于**： Outlook 
  
创建一个名为的结构包含用于描述的选项卡式的页面控件、 标签指定长度的和具有指定长度的帮助文件项[DTBLPAGE](dtblpage.md)结构。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**DTBLPAGE** <br/> |
   
```cpp
SizedDtblPage (n, n1, u)
```

## <a name="parameters"></a>参数

_n_
  
> 页面选项卡的标签的长度。
    
_n1_
  
> 确定将用于选项卡式的页面控件的帮助文件的 Mapisvc.inf 文件中显示该词条的长度。
    
_u_
  
> 新结构的的名称。
    
## <a name="remarks"></a>说明

**SizedDtblPage**宏允许您定义的选项卡式的页面控件时已知的关联的标签名称和帮助文件项中的字符数。 使用下列成员来创建新的结构： 
  
```cpp
DTBLPAGE dtblpage;
TCHAR lpszLabel[n];
TCHAR lpszComponent[n1];
```

若要将指针生成结构从**SizedDtblPage**宏作为**DTBLPAGE**结构指针，执行以下的强制转换： 
  
```cpp
lpDtblPage = (LPDTBLPAGE) &SizedDtblPage;
```

## <a name="see-also"></a>另请参阅

- [DTBLPAGE](dtblpage.md)
- [与结构相关的宏](macros-related-to-structures.md)

