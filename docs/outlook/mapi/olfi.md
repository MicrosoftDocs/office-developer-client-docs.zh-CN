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
  
由个人文件夹文件或 PST) 存储提供程序使用的长期 (ID 结构队列，用于在脱机模式下分配新邮件或文件夹的条目 ID。
  
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
  
- 此成员仅供内部使用，Outlook不支持。
    
 _ulReserved_
  
- 此成员仅供内部使用，Outlook不支持。
    
 _dwAlloc_
  
- 可用于分配的条目数。 这些条目与 GUID 共享相同的全局唯 (标识符) 。
    
 _dwNextAlloc_
  
- 下一步可用于分配的条目数。 这些条目共享相同的 GUID。
    
 _ltidAlloc_
  
- 长期 ID 结构 **[LTID，](ltid.md)** 用于标识当前可用于分配的条目。 长期 ID 结构包含一个 GUID 和一个标识存储区中的对象的索引。 GUID 和索引共同构成对象的唯一条目 ID。 
    
 _ltidNextAlloc_
  
- 用于标识下一个可用条目的长期 ID 结构。
    
## <a name="remarks"></a>备注

条目 ID 是文件夹或邮件的 4 字节 MAPI 条目标识符。 有关详细信息，请参阅 [ENTRYID](https://msdn.microsoft.com/library/ms836424)。
  
当 PST 存储提供程序向新对象分配条目 ID 时，它首先需要一个标识服务器的 GUID 和一个标识存储中的对象的索引。 即使 GUID 并非在所有条目标识中都是唯一的，但 GUID 和索引组合可以提供唯一的条目。 此 GUID 和索引对由作为 **OLFI** 结构的一部分的长期 ID 结构 **LTID** 进行跟踪。 
  
PST 存储提供程序实际上不会在每个 GUID 索引对的 **OLFI** 中保留 **LTID** 结构。 它为当前第一个可用的 GUID 索引对保留一个 **LTID** 结构  *ltidAlloc;*  共享此相同 GUID 的可用条目数量的计数  *dwAlloc;*  和另一 **个 LTID** 结构  *ltidNextAlloc，*  用于下一个具有不同的 GUID 的可用 GUID 索引对。 PST 存储提供程序使用 **OLFI** 结构跟踪已提供 GUID 和索引。在虚拟级别，提供程序保留大量准备分配的 **LTID** 结构。  *dwAlloc*  维护可用 **LTID 结构的** 计数。 
  
对条目 ID 的请求以块表示。 当有阻止请求时，PST 存储提供程序会通过将请求的大小与  *dwAlloc*  进行比较来检查是否有足够的保留。 如果有足够的保留，它将在  *ltidAlloc*  中返回 GUID 和索引进行分配。 然后，它将  *dwAlloc*  减小为请求的大小，并按请求的大小增加  *ltidAlloc*  中的索引。 这将准备 PST 存储提供程序在下次请求另一个条目 ID 块时分配 *ltidAlloc。* 请注意，对于下一个请求，GUID 保持不变。 
  
如果请求的大小大于  *dwAlloc*  ，PST 存储提供程序将尝试使用它下一个保留项，如  *dwNextAlloc*  和  *ltidNextAlloc 所指定*  。 它将  *dwNextAlloc 和*  *ltidNextAlloc*  分别复制到  *dwAlloc*  和  *ltidAlloc，*  将  *dwNextAlloc*  和  *ltidNextAlloc*  分别设置为 NULL。 
  
包装 PST 存储提供程序的提供商应定期检查  *ltidNextAlloc*  以查看其是否为 NULL。 如果是，提供程序应该使用新的 GUID 填充它并重置  *dwNextAlloc，*  以便可以分配更多的条目 ID。 
  
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)
  
[关于复制状态机](about-the-replication-state-machine.md)
  
[LTID](ltid.md)

