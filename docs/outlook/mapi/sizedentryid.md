---
title: SizedENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedENTRYID
api_type:
- COM
ms.assetid: 491170af-db35-4d7e-a912-44ffe8c7506b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 814cfeab61854469f460cc38f927b0e3723f6f0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778795"
---
# <a name="sizedentryid"></a>SizedENTRYID

**适用于**： Outlook 
  
创建包含的指定大小**ab**成员的命名的[ENTRYID](entryid.md)结构。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的结构：  <br/> |**ENTRYID** <br/> |
   
```cpp
SizedENTRYID (_cb, _name)
```

## <a name="parameters"></a>参数

__cb_
  
> 在新结构的**ab**成员的字节数。 
    
__名称_
  
> 新结构的的名称。
    
## <a name="remarks"></a>说明

**SizedENTRYID**宏允许您定义的项标识符后已知数组长度要求。 使用此宏来使用显式边界创建的项标识符。 
  
若要使用新结构的结果从**SizedENTRYID**宏作为指针指向**ENTRYID**结构，执行下列转换： 
  
```cpp
lpENTRYID = (LPENTRYID) &SizedENTRYID;

```

## <a name="see-also"></a>另请参阅

- [ENTRYID](entryid.md)
- [与结构相关的宏](macros-related-to-structures.md)

