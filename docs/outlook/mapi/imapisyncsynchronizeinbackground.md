---
title: IMAPISync SynchronizeInBackground
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISync.SynchronizeInBackground
api_type:
- COM
ms.assetid: c4aaca65-d553-476c-8c6d-5f880b6efdc1
description: 上次修改时间：2012 年 6 月 26 日
ms.openlocfilehash: 108073f5e4833d9641e67065eb642320352fffe4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426854"
---
# <a name="imapisync--synchronizeinbackground"></a>IMAPISync : SynchronizeInBackground

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 启动同步。 此方法由 microsoft outlook 2010 和 microsoft outlook 2013 调用, 并由邮件存储提供程序实现。 
  
```cpp
HRESULT SynchronizeInBackground (
  PMAPISIB psibpb
);
```

## <a name="parameters"></a>参数

 _psibpb_
  
> 通知提供程序将进行同步, 并提供对可在同步过程中使用的接口的访问权限。 它是一个[MAPISIB](mapisib.md)结构。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="see-also"></a>另请参阅



[IMAPISync : IUnknown](imapisynciunknown.md)
  
[MAPISIB](mapisib.md)

