---
title: LTID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17a412ba-3f74-ba94-0ffa-01dae63fc157
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 29dd2e3b47d0f43df7824274d2fdcc4f7f16eeb3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569853"
---
# <a name="ltid"></a>LTID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
Outlook 存储区中某个对象的通用长术语 ID。
  
## <a name="quick-info"></a>快速信息

```cpp
struct LTID 
{ 
    GUID guid; 
    BYTE globcnt[6]; 
    WORD wLevel; 
};
```

## <a name="members"></a>Members

 _guid_
  
- [输出]创建对象的服务器的 GUID。
    
 _globcnt_
  
- [输出]标识的 Outlook 存储中的对象的 6 个字节唯一编号。
    
 _wLevel_
  
- [输出]Exchange 喜欢公用文件夹的条目 ID 层次结构级别。
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[FEID](feid.md)

