---
title: IPSTXGetSyncObject
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTX.GetSyncObject
api_type:
- COM
ms.assetid: b93dae79-4305-9a3a-7b93-42319f7e26ba
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e0e27d86098ec55849fa96cc150c60934ef2810b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585449"
---
# <a name="ipstxgetsyncobject"></a>IPSTX::GetSyncObject

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
启动同步会话，并获取相关联的**[IOSTX](iostxiunknown.md)** 接口。 
  
```cpp
HRESULT GetSyncObject( 
   IOSTX **ppostx 
);
```

## <a name="parameters"></a>参数

 _ppostx_
  
>  [输出]指向要获取的**IOSTX**接口的指针。 
    
## <a name="remarks"></a>注解

呼叫者必须确保同时在多个线程上不同步的相同的文件夹。
  
## <a name="see-also"></a>另请参阅



[IPSTX::EmulateSpooler](ipstx-emulatespooler.md)
  
[IPSTX::GetLastError](ipstx-getlasterror.md)

