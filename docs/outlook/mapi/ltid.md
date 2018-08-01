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
ms.openlocfilehash: 4a60e2fe3a58e1d696ae9645e03ce8dde5340d9a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776155"
---
# <a name="ltid"></a>LTID

  
  
**适用于**： Outlook 
  
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

