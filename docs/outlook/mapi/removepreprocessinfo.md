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
ms.openlocfilehash: d80c73aef780a0da39f3939f71462488a067de5f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328376"
---
# <a name="removepreprocessinfo"></a>RemovePreprocessInfo

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从邮件中删除基于[PreprocessMessage](preprocessmessage.md)的函数编写的经过预处理的信息。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|定义的函数实现者:  <br/> |传输提供程序  <br/> |
|定义的函数调用者:  <br/> |MAPI 后台处理程序  <br/> |
   
```cpp
HRESULT RemovePreprocessInfo(
  LPMESSAGE lpMessage
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> 实时指向要从中删除信息的预处理邮件的指针。
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功删除已预处理的信息。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用基于**RemovePreprocessInfo**的函数。 在对[IMAPISupport:: RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法的调用中注册基于并行**PreprocessMessage**的函数时, 传输提供程序会同时注册基于**RemovePreprocessInfo**的函数。 
  
适合传真传输的图像呈现是由[PreprocessMessage](preprocessmessage.md)函数原型定义的函数编写的经过预处理的信息的示例。 MAPI 后台处理程序通常在发送包含经过预处理的信息的邮件后调用**RemovePreprocessInfo**函数。 
  

