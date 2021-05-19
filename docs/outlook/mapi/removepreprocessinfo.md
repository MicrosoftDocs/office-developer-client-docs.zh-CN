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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432945"
---
# <a name="removepreprocessinfo"></a>RemovePreprocessInfo

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从邮件中删除由基于 [PreprocessMessage](preprocessmessage.md) 的函数写入的预处理信息。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi.h  <br/> |
|定义的函数实现方：  <br/> |传输提供程序  <br/> |
|由调用的已定义函数：  <br/> |MAPI 后台处理程序  <br/> |
   
```cpp
HRESULT RemovePreprocessInfo(
  LPMESSAGE lpMessage
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> [in]指向将从中删除信息的预处理邮件的指针。
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功删除预处理的信息。
    
## <a name="remarks"></a>备注

MAPI 后台处理程序调用基于 **RemovePreprocessInfo 的函数**。 传输提供程序在注册基于 **RemovePreprocessInfo** 的函数的同时，在 [调用 IMAPISupport：：RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法时注册基于 **PreprocessMessage** 的并行函数。 
  
适用于传真传输的图像呈现是由 [PreprocessMessage](preprocessmessage.md)函数原型定义的函数编写的预处理信息的示例。 MAPI 后台处理程序通常在发送包含预处理信息的邮件后调用 **RemovePreprocessInfo** 函数。 
  

