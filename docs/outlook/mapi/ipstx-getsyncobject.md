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
ms.openlocfilehash: 44261e5ac296004fd113d4c9123b99c482bcb732
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776065"
---
# <a name="ipstxgetsyncobject"></a>IPSTX::GetSyncObject

  
  
**适用于**： Outlook 
  
启动同步会话，并获取相关联的**[IOSTX](iostxiunknown.md)** 接口。 
  
```cpp
HRESULT GetSyncObject( 
   IOSTX **ppostx 
);
```

## <a name="parameters"></a>参数

 _ppostx_
  
>  [输出]指向要获取的**IOSTX**接口的指针。 
    
## <a name="remarks"></a>说明

呼叫者必须确保同时在多个线程上不同步的相同的文件夹。
  
## <a name="see-also"></a>另请参阅



[IPSTX::EmulateSpooler](ipstx-emulatespooler.md)
  
[IPSTX::GetLastError](ipstx-getlasterror.md)

