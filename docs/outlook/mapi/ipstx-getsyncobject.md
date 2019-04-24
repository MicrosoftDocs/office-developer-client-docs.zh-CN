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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 31ef1f5c6af498f042ab766ae90fcfbce805700a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315083"
---
# <a name="ipstxgetsyncobject"></a>IPSTX::GetSyncObject

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启动同步会话并获取关联的**[IOSTX](iostxiunknown.md)** 接口。 
  
```cpp
HRESULT GetSyncObject( 
   IOSTX **ppostx 
);
```

## <a name="parameters"></a>参数

 _ppostx_
  
>  排除指向要获取的**IOSTX**接口的指针。 
    
## <a name="remarks"></a>注解

调用方必须确保同一个文件夹不会同时在多个线程上同步。
  
## <a name="see-also"></a>另请参阅



[IPSTX::EmulateSpooler](ipstx-emulatespooler.md)
  
[IPSTX::GetLastError](ipstx-getlasterror.md)

