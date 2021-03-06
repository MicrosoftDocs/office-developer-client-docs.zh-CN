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
ms.openlocfilehash: f14b8d7a9a73997f797f9cfa26a2e574222e839e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407443"
---
# <a name="sizeddtblpage"></a>SizedDtblPage

**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个命名结构，其中包含用于描述选项卡式页面控件的 [DTBLPAGE](dtblpage.md) 结构、指定长度的标签和指定长度的帮助文件条目。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关结构：  <br/> |**DTBLPAGE** <br/> |
   
```cpp
SizedDtblPage (n, n1, u)
```

## <a name="parameters"></a>参数

_n_
  
> 页面选项卡的标签长度。
    
_n1_
  
> Mapisvc.inf 文件中用于标识将用于选项卡式页面控件的帮助文件条目的长度。
    
_u_
  
> 新结构的名称。
    
## <a name="remarks"></a>备注

**SizedDtblPage** 宏允许您在关联的标签和帮助文件条目中的字符数已知时定义选项卡式页面控件。 新结构由以下成员创建： 
  
```cpp
DTBLPAGE dtblpage;
TCHAR lpszLabel[n];
TCHAR lpszComponent[n1];
```

若要将指向 **SizedDtblPage** 宏生成的结构的指针用作 **DTBLPAGE** 结构指针，请执行以下转换： 
  
```cpp
lpDtblPage = (LPDTBLPAGE) &SizedDtblPage;
```

## <a name="see-also"></a>另请参阅

- [DTBLPAGE](dtblpage.md)
- [与结构相关的宏](macros-related-to-structures.md)

