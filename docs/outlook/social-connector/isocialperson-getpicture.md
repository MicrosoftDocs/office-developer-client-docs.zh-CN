---
title: ISocialPersonGetPicture
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 02fcaf25-42b5-4584-95c6-d44a3d035128
description: 获取包含此人的图片资源的字节数组。
ms.openlocfilehash: dcb0da5bc36c2166d569c770d1f182cd21339435
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779210"
---
# <a name="isocialpersongetpicture"></a>ISocialPerson::GetPicture

获取包含此人的图片资源的字节数组。 
  
```cpp
HRESULT _stdcall GetPicture([out, retval] SAFEARRAY(unsigned char)* picture);
```

## <a name="parameters"></a>参数

_图片_
  
> [输出]一个指向指定一个表示图片资源的人员的字节数组的结构。
    
## <a name="remarks"></a>说明

支持资源是.bmp、.jpeg 或.png 格式中的图片。
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson : IUnknown](isocialpersoniunknown.md)

