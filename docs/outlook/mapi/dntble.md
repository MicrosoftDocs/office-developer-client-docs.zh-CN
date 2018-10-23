---
title: DNTBLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 10fb1650-6c3e-f467-91cd-48e5ddd82827
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: 41a61bd05bd511888aeab756166016813f4dceb8
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391946"
---
# <a name="dntble"></a>DNTBLE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在[下载表状态](download-table-state.md)期间从服务器下载文件夹内容的信息。 这一下载过程使用 Microsoft Exchange 增量更改同步 (ICS)。 有关 ICS 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。
  
## <a name="quick-info"></a>快速信息

```cpp
struct DNTBLE 
{ 
    UINT cEntNew; 
    UINT cEntMod; 
    UINT cEntRead; 
    UINT cEntDel; 
};
```

## <a name="members"></a>成员

 _cEntNew_
  
> [传出] 添加到本地存储的项数。 Outlook 在下载期间使用 ICS 时填充此值。
    
 _cEntMod_
  
> [传出] 本地存储上已修改的项数。 Outlook 在下载期间使用 ICS 时填充此值。
    
 _cEntRead_
  
> [传出] 本地存储上已读或标记为未读的项数。 Outlook 在下载期间使用 ICS 时填充此值。
    
 _cEntDel_
  
> [传出] 本地存储上已删除的项数。 Outlook 在下载期间使用 ICS 时填充此值。
    
## <a name="see-also"></a>另请参阅



[关于复制状态机](about-the-replication-state-machine.md)
  
[MAPI 常量](mapi-constants.md)
  
[DNTBL](dntbl.md)

