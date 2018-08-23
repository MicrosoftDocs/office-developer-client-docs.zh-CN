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
ms.openlocfilehash: e9a1c416cbf992c9cbcfb5de42d302ff16e7f521
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573185"
---
# <a name="msgcallrelease"></a>MSGCALLRELEASE

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
定义一个在它构建与[OpenIMsgOnIStg](openimsgonistg.md)函数**IMessage**对象的最终发行后可以释放**IStorage**接口的回调函数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Imessage.h  <br/> |
|通过实施定义的函数：  <br/> |客户端应用程序和服务提供商  <br/> |
|定义的函数调用：  <br/> |MAPI  <br/> |
   
```cpp
typedef void (STDAPICALLTYPE MSGCALLRELEASE)(
  ULONG  ulCallerData,
  LPMESSAGE  lpMessage );
```

## <a name="parameters"></a>参数

 _ulCallerData_
  
> [in]包含有关**IMessage**接口调用应用程序信息。 
    
 _lpMessage_
  
> [in]顶级邮件和附件的已发布的指针。
    
## <a name="return-value"></a>返回值

无。
  

