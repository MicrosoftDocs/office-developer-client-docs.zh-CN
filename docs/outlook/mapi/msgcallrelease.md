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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405910"
---
# <a name="msgcallrelease"></a>MSGCALLRELEASE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义一个回调函数，该函数可在 **IMessage** 对象最终发布后使用 [OpenIMsgOnIStg](openimsgonistg.md)函数释放 **IStorage** 接口。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage.h  <br/> |
|定义的函数实现方：  <br/> |客户端应用程序和服务提供商  <br/> |
|由调用的已定义函数：  <br/> |MAPI  <br/> |
   
```cpp
typedef void (STDAPICALLTYPE MSGCALLRELEASE)(
  ULONG  ulCallerData,
  LPMESSAGE  lpMessage );
```

## <a name="parameters"></a>参数

 _ulCallerData_
  
> [in]包含有关 **IMessage 接口的调用应用程序** 信息。 
    
 _lpMessage_
  
> [in]指向已释放的顶级邮件和附件的指针。
    
## <a name="return-value"></a>返回值

无。
  

