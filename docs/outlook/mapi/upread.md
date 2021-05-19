---
title: UPREAD
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 568f2336-cb4d-3f2c-a304-d29cdb0bcbcc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7338edc13227e303ec5fa47da4a5d9ee611c6749
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419882"
---
# <a name="upread"></a>UPREAD

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在上传读取状态期间上传项目的 [读取状态的信息](upload-read-status-state.md)。
  
## <a name="quick-info"></a>快速信息

```cpp
struct UPREAD 
{ 
    PUPREADE pupre; 
    UINT cEnt; 
};
```

## <a name="members"></a>成员

 _pupre_
  
>  [out] **[UPREADE 条目的](upreade.md)** 矢量。 
    
 _cEnt_
  
>  [out] **UPREADE 条目** 的数量。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)
  
[UPREADE](upreade.md)

