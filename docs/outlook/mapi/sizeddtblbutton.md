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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a7d62d29638ae234667eb33a8103fb3a716afc32
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421912"
---
# <a name="sizeddtblbutton"></a>SizedDtblButton

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建一个命名结构，其中包含用于描述按钮和指定长度的标签的 [DTBLBUTTON](dtblbutton.md) 结构。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关结构：  <br/> |**DTBLBUTTON** <br/> |
   
```cpp
SizedDtblButton (n, u)
```

## <a name="parameters"></a>参数

 _n_
  
> 要包含在新结构中的标签的长度。
    
 _u_
  
> 新结构的名称。
    
## <a name="remarks"></a>备注

新结构由以下成员创建：
  
```
DTBLBUTTON dtblbutton;
TCHAR lpszLabel[n];

```

## <a name="see-also"></a>另请参阅



[DTBLBUTTON](dtblbutton.md)


[与结构相关的宏](macros-related-to-structures.md)

