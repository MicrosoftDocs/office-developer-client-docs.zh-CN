---
title: RemovePreprocessInfo
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.RemovePreprocessInfo
api_type:
- COM
ms.assetid: 25f46937-abac-4a0b-83db-eeac9451c112
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fab8860621cee5a87b087ee9d98f373baa278e45
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778641"
---
# <a name="removepreprocessinfo"></a>RemovePreprocessInfo

  
  
**适用于**： Outlook 
  
删除预处理信息写入由[PreprocessMessage](preprocessmessage.md)基于函数从一条消息。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
|通过实施定义的函数：  <br/> |传输提供程序  <br/> |
|定义的函数调用：  <br/> |MAPI 后台处理程序  <br/> |
   
```cpp
HRESULT RemovePreprocessInfo(
  LPMESSAGE lpMessage
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> [in]是要移除信息预处理邮件的指针。
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功删除预处理的信息。
    
## <a name="remarks"></a>说明

MAPI 后台处理程序调用基于**RemovePreprocessInfo**函数。 传输提供程序注册它对[IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法的调用中注册的并行**PreprocessMessage**基于函数的同时**RemovePreprocessInfo**基于函数。 
  
图像呈现适合传真传输是预处理信息由的[PreprocessMessage](preprocessmessage.md)函数原型定义的函数编写的示例。 MAPI 后台处理程序通常发送一条消息，包含预处理的信息后调用**RemovePreprocessInfo**函数。 
  

