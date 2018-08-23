---
title: IMAPIFormInfoOpenFormContainer
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo.OpenFormContainer
api_type:
- COM
ms.assetid: 1d6eec99-59f9-4700-9b83-7f7f8787a9f8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 16e1d45806755bad8caff6847b0ecdea5b4ba78b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590419"
---
# <a name="imapiforminfoopenformcontainer"></a>IMAPIFormInfo::OpenFormContainer

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回到安装了特定的窗体的窗体容器的指针。
  
```cpp
HRESULT OpenFormContainer(
  LPMAPIFORMCONTAINER FAR * ppformcontainer
);
```

## <a name="parameters"></a>参数

 _ppformcontainer_
  
> [输出]指向返回窗体容器对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="see-also"></a>另请参阅



[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)

