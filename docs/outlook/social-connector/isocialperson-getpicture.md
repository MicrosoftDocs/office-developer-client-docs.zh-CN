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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406708"
---
# <a name="isocialpersongetpicture"></a>ISocialPerson::GetPicture

获取包含人员的图片资源的字节数组。 
  
```cpp
HRESULT _stdcall GetPicture([out, retval] SAFEARRAY(unsigned char)* picture);
```

## <a name="parameters"></a>参数

_picture_
  
> [out]指向指定字节数组的结构的指针，该数组代表人员的图片资源。
    
## <a name="remarks"></a>备注

支持的图片资源采用 .bmp、.jpeg 或 .png 格式。
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson : IUnknown](isocialpersoniunknown.md)

