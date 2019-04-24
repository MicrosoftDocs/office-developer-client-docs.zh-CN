---
title: MSGCALLRELEASE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MSGCALLRELEASE
api_type:
- COM
ms.assetid: 23c08597-41f0-4f48-a63e-79962fa812bc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9ffaab1e9cc381be2abfb389f4b72067dca2438b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338561"
---
# <a name="msgcallrelease"></a>MSGCALLRELEASE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义一个回调函数, 该函数可以在使用[OpenIMsgOnIStg](openimsgonistg.md)函数的基础之上生成的**IMessage**对象的最终发布后释放**IStorage**接口。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage  <br/> |
|定义的函数实现者:  <br/> |客户端应用程序和服务提供程序  <br/> |
|定义的函数调用者:  <br/> |MAPI  <br/> |
   
```cpp
typedef void (STDAPICALLTYPE MSGCALLRELEASE)(
  ULONG  ulCallerData,
  LPMESSAGE  lpMessage );
```

## <a name="parameters"></a>参数

 _ulCallerData_
  
> 实时包含有关**IMessage**接口的调用应用程序信息。 
    
 _lpMessage_
  
> 实时指向顶级邮件的指针以及已发布的附件。
    
## <a name="return-value"></a>返回值

无。
  

