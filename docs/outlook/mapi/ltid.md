---
title: LTID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17a412ba-3f74-ba94-0ffa-01dae63fc157
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2ea877c9328279322de0f15e5755096e74819425
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419434"
---
# <a name="ltid"></a>LTID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Outlook 应用商店中的对象的常规长期术语 ID。
  
## <a name="quick-info"></a>快速信息

```cpp
struct LTID 
{ 
    GUID guid; 
    BYTE globcnt[6]; 
    WORD wLevel; 
};
```

## <a name="members"></a>成员

 _guid_
  
- 排除创建该对象的服务器的 GUID。
    
 _globcnt_
  
- 排除一个6字节的唯一编号, 用于标识 Outlook 存储中的对象。
    
 _wLevel_
  
- 排除Exchange 收藏的公用文件夹的条目 ID 的层次结构级别。
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[FEID](feid.md)

