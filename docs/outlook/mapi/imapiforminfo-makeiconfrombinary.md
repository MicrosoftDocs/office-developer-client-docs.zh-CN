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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 418056f7222d5ab05f43a3661c1811bf2ae15be8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405112"
---
# <a name="imapiforminfomakeiconfrombinary"></a>IMAPIFormInfo::MakeIconFromBinary

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从窗体的图标属性之一生成图标。
  
```cpp
HRESULT MakeIconFromBinary(
  ULONG nPropID,
  HICON FAR * phicon
);
```

## <a name="parameters"></a>参数

 _nPropID_
  
> 实时icon 属性的属性标识符。
    
 _phicon_
  
> 排除指向返回图标的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

客户端应用程序调用**IMAPIFormInfo:: MakeIconFromBinary**方法, 以根据窗体的图标属性之一构建图标。 在_nPropID_参数中, **MakeIconFromBinary**采用表单的图标属性之一的属性标识符。 使用此属性标识符, 它将构建一个图标, 该图标可显示在包含图标属性列的表格视图中。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)

