---
title: OLFI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 44bfaadf-36f9-bd8e-6158-646533f6849e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 027905721b5730b4c3d78f496022b88a8e6b84d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279751"
---
# <a name="olfi"></a>OLFI

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
个人文件夹文件 (PST) 存储提供程序用于为脱机模式中的新邮件或文件夹分配条目 id 的长期 ID 结构队列。
  
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

## <a name="members"></a>成员

 _ulVersion_
  
- 结构的版本号。 
    
 _muidReserved_
  
- 此成员是为内部使用 Outlook 而保留的, 不受支持。
    
 _ulReserved_
  
- 此成员是为内部使用 Outlook 而保留的, 不受支持。
    
 _dwAlloc_
  
- 可分配的条目数。 这些条目共享相同的全局唯一标识符 (GUID)。
    
 _dwNextAlloc_
  
- 用于分配的下一个条目的数量。 这些条目共享相同的 GUID。
    
 _ltidAlloc_
  
- 长期 ID 结构, **[LTID](ltid.md)**, 用于标识当前可供分配的条目。 长期 ID 结构包含一个 GUID 和一个索引, 用于标识存储区中的对象。 GUID 和索引可以构成对象的唯一条目 ID。 
    
 _ltidNextAlloc_
  
- 长期 ID 结构, 用于标识下一个可用的条目。
    
## <a name="remarks"></a>注解

条目 ID 是文件夹或邮件的4字节 MAPI 条目标识符。 有关详细信息, 请参阅[ENTRYID](https://msdn.microsoft.com/library/ms836424)。
  
当 PST 存储提供程序将条目 ID 分配给新对象时, 它首先需要一个标识服务器的 GUID 以及一个标识存储中的对象的索引。 尽管 guid 在所有条目 id 中不是唯一的, 但 guid 和索引组合提供了唯一的条目。 此 GUID 和索引对由长期 ID 结构 ( **LTID**) 跟踪, 后者是**OLFI**结构的一部分。 
  
PST 存储提供程序不会在物理上保留每个 GUID 索引对的**LTID**结构**OLFI** 。 它保留一个**LTID**结构*ltidAlloc* , 用于当前的第一个可用的 GUID 索引对;共享此同一 GUID 的可用条目数的计数、 *dwAlloc* 、第二个**LTID**结构, *ltidNextAlloc* , 用于具有不同 guid 的下一个可用的 guid 索引对。 PST 存储提供程序使用**OLFI**结构跟踪已提交的 guid 和索引。在虚拟级别, 提供程序保留准备分配的大量**LTID**结构的保留。  *dwAlloc*维护可用的**LTID**结构的计数。 
  
条目 id 请求进入块。 当对块发出请求时, PST 存储提供程序将通过将请求的大小与*dwAlloc*进行比较来检查是否有足够的预留。 如果有足够的准备金, 它将在*ltidAlloc*中返回 GUID 和索引以进行分配。 然后, 它将*dwAlloc*减小请求的大小, 并根据请求的大小增加*ltidAlloc*中的索引。 这将为 PST 存储提供程序准备在下一个条目 id 块的下一个请求上分配*ltidAlloc* 。 请注意, 对于下一个请求, GUID 保持不变。 
  
如果请求的大小大于*dwAlloc* , PST 存储提供程序将尝试使用*dwNextAlloc*和*ltidNextAlloc*指定的下一个保留内容。 它分别将*dwNextAlloc*和*ltidNextAlloc*复制到*dwAlloc*和*ltidAlloc* , 并将*dwNextAlloc*和*ltidNextAlloc*设置为 NULL。 
  
包装 PST 存储提供程序的提供程序应定期检查*ltidNextAlloc* , 以查看它是否为 NULL。 如果是, 则提供程序应使用新的 GUID 填充它并重置*dwNextAlloc* , 以便可以分配更多的条目 id。 
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[LTID](ltid.md)

