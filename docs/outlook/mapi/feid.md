---
title: FEID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2dde7eec-df3d-723c-db08-7ff0b6107a0b
description: '上次修改时间: 2012 年7月2日'
ms.openlocfilehash: 88716719857cfd623d30a3684fc997ea8019455e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409809"
---
# <a name="feid"></a>FEID

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
文件夹的标识符。 它包含条目标识符和其他相关信息。
  
## <a name="quick-info"></a>快速信息

```cpp
struct FEID 
{ 
    BYTE abFlags[4]; 
    MAPIUID muid; 
    WORD placeholder; 
    LTID ltid; 
};
```

## <a name="members"></a>成员

 _abFlags_
  
> 4字节的文件夹的条目标识符。 有关 MAPI 条目标识符的详细信息, 请参阅**[ENTRYID](entryid.md)**。 
    
 _muid_
  
> 标识存储提供程序的 GUID。 有关**MAPIUID**的类型定义, 请参阅 mapidefs.h。 
    
 _占位符_
  
> 此成员是为内部使用 Outlook 而保留的, 不受支持。
    
 _ltid_
  
> 文件夹的长期 ID。
    
## <a name="see-also"></a>另请参阅



[关于复制状态机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)
  
[LTID](ltid.md)
  
[UPFLD](upfld.md)
  
[同步](sync.md)

