---
title: SizedDtblButton
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblButton
api_type:
- COM
ms.assetid: ee73ced9-14d8-4a30-9b9f-d54ed9c3a454
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 3de56b12fa7d34004fddbfe3633b8b8307c0ffc1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778782"
---
# <a name="sizeddtblbutton"></a>SizedDtblButton

  
  
**适用于**： Outlook 
  
创建一个名为的结构包含用于描述一个按钮和一个指定长度的标签[DTBLBUTTON](dtblbutton.md)结构。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**DTBLBUTTON** <br/> |
   
```cpp
SizedDtblButton (n, u)
```

## <a name="parameters"></a>参数

 _n_
  
> 标签的新结构中包含的长度。
    
 _u_
  
> 新结构的的名称。
    
## <a name="remarks"></a>备注

使用下列成员来创建新的结构：
  
```
DTBLBUTTON dtblbutton;
TCHAR lpszLabel[n];

```

## <a name="see-also"></a>另请参阅



[DTBLBUTTON](dtblbutton.md)


[与结构相关的宏](macros-related-to-structures.md)

