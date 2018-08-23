---
title: IMAPIFormInfoMakeIconFromBinary
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo.MakeIconFromBinary
api_type:
- COM
ms.assetid: 4daeddd7-3f0c-4178-ae8d-f74814090d40
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 30f55044327eecee3ab0d8ee2509d7132ab6e8ee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570126"
---
# <a name="imapiforminfomakeiconfrombinary"></a>IMAPIFormInfo::MakeIconFromBinary

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
生成来自窗体的图标属性之一的图标。
  
```cpp
HRESULT MakeIconFromBinary(
  ULONG nPropID,
  HICON FAR * phicon
);
```

## <a name="parameters"></a>参数

 _nPropID_
  
> [in]Icon 属性属性标识符。
    
 _phicon_
  
> [输出]指向返回图标的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>注解

客户端应用程序调用**IMAPIFormInfo::MakeIconFromBinary**方法生成来自窗体的图标属性之一的图标。 _NPropID_参数中**MakeIconFromBinary**所需窗体的图标属性之一属性的标识符。 使用此属性标识符，它构建可包含图标的属性列的表视图中显示的图标。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)

