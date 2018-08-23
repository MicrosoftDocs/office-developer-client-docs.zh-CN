---
title: OLFI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 44bfaadf-36f9-bd8e-6158-646533f6849e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7d01f07b5eb5ca34b4bd825b62b7d1520b853d6b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564260"
---
# <a name="olfi"></a>OLFI

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
个人文件夹文件 (PST) 存储提供程序用于分配新的邮件或文件夹在脱机模式下的条目 ID 的长期 ID 结构的队列。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    ULONG    ulVersion; 
    MAPIUID  muidReserved; 
    ULONG    ulReserved; 
    DWORD    dwAlloc; 
    DWORD    dwNextAlloc; 
    LTID     ltidAlloc; 
    LTID     ltidNextAlloc; 
} OLFI, *POLFI;
```

## <a name="members"></a>Members

 _ulVersion_
  
- 结构的版本号。 
    
 _muidReserved_
  
- 此成员仅供内部使用的 Outlook，不支持。
    
 _ulReserved_
  
- 此成员仅供内部使用的 Outlook，不支持。
    
 _dwAlloc_
  
- 供分配的条目数。 这些条目共享相同的全局唯一标识符 (GUID)。
    
 _dwNextAlloc_
  
- 分配下一步是可用的条目数。 这些条目共享相同的 GUID。
    
 _ltidAlloc_
  
- 长期 ID 结构， **[LTID](ltid.md)**，标识当前可用于分配条目。 长期 ID 结构包含一个 GUID 和识别存储区中的对象的索引。 在一起，GUID 和索引形成对象的唯一的条目 ID。 
    
 _ltidNextAlloc_
  
- 标识的下一个可用的条目的长期 ID 结构。
    
## <a name="remarks"></a>注解

条目 ID 是 4 字节 MAPI 项标识符的文件夹或一条消息。 有关详细信息，请参阅[ENTRYID](http://msdn.microsoft.com/en-us/library/ms836424)。
  
当 PST 存储提供程序将条目 ID 分配给一个新的对象时，首先需要标识服务器的 GUID 和标识存储区中的对象的索引。 即使跨所有条目 Id GUID 不唯一，GUID 和索引组合将提供一个唯一的项。 此 GUID 和索引对跟踪通过长期的 ID 结构**LTID**，这是**OLFI**结构的一部分。 
  
PST 存储提供程序不会从物理上隔离保留**OLFI**中的每个 GUID 索引对**LTID**结构。 它会保留一个**LTID**结构， *ltidAlloc* ，当前第一个可用的 GUID 索引对;count， *dwAlloc* ，可用共享此相同的 GUID; 的项的数目和第二个**LTID**结构*ltidNextAlloc*下, 一步的可用 GUID 索引对具有不同的 GUID。 PST 存储提供程序使用**OLFI**结构，以跟踪 Guid 和它具有分发的索引。在虚拟级别，提供程序维护储备数**LTID**结构已准备好进行分配。  *dwAlloc*维护可用**LTID**结构的计数。 
  
请求条目 Id 前置块中。 存在块的请求时，请 PST 存储提供程序将检查是否存在足够保留现有通过比较*dwAlloc*与请求的大小。 如果没有足够的保留，它返回 GUID 和索引中的分配*ltidAlloc* 。 然后*dwAlloc*减少请求的大小，并在*ltidAlloc*索引递增请求的大小。 此准备的条目 Id 的另一个块分配下一个请求*ltidAlloc* PST 存储提供程序。 请注意 GUID 保持不变的下一个请求。 
  
如果请求的大小大于*dwAlloc* ，PST 存储提供程序尝试使用它在下一步具有的作预备，由*dwNextAlloc*和*ltidNextAlloc*指定。 它分别将*dwNextAlloc*和*ltidNextAlloc*复制到*dwAlloc*和*ltidAlloc* ，并将*dwNextAlloc*和*ltidNextAlloc*设置为 NULL。 
  
换行的 PST 存储提供程序的提供程序应定期检查*ltidNextAlloc*为 NULL。 如果是，提供程序应填充使用新的 GUID，并重置*dwNextAlloc* ，以便可以分配多个条目 Id。 
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态计算机](about-the-replication-state-machine.md)
  
[LTID](ltid.md)

