---
title: ISocialPersonGetPicture
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 02fcaf25-42b5-4584-95c6-d44a3d035128
description: 获取包含人员的图片资源的字节数组。
ms.openlocfilehash: 755e2138378136a3c1d810a1957923f4e8db721d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331652"
---
# <a name="isocialpersongetpicture"></a>ISocialPerson::GetPicture

获取包含人员的图片资源的字节数组。 
  
```cpp
HRESULT _stdcall GetPicture([out, retval] SAFEARRAY(unsigned char)* picture);
```

## <a name="parameters"></a>参数

_头像_
  
> 排除指向结构的指针, 该结构指定代表人员的图片资源的字节数组。
    
## <a name="remarks"></a>注解

支持的图片资源采用 .bmp、jpeg 或 .png 格式。
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson : IUnknown](isocialpersoniunknown.md)

