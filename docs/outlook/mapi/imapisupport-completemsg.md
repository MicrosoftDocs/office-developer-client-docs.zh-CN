---
title: IMAPISupportCompleteMsg
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CompleteMsg
api_type:
- COM
ms.assetid: e7932433-abe0-4341-95e0-91b37c848145
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: db28d9684f1bb679ce36f99346f4ecc67a1a93e6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19775598"
---
# <a name="imapisupportcompletemsg"></a>IMAPISupport::CompleteMsg

  
  
**适用于**： Outlook 
  
执行上一条消息后处理。 
  
```cpp
HRESULT CompleteMsg(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要处理的消息的项标识符的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 后处理过程成功。
    
## <a name="remarks"></a>注解

**IMAPISupport::CompleteMsg**方法实现的消息存储提供程序支持对象和只能由与传输提供程序紧密耦合的消息存储提供程序调用。 紧密耦合的存储提供程序调用**IMAPISupport::CompleteMsg**以指示 MAPI 后台处理程序后置处理一条消息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

仅当紧密结合传输提供程序，您可以处理所有收件人，并且存在以下情况之一时，请调用**CompleteMsg** : 
  
- 邮件已预处理。
    
- 邮件需要后处理 MAPI 后台打印程序。
    
## <a name="see-also"></a>另请参阅



[IMAPISupport: IUnknown](imapisupportiunknown.md)

