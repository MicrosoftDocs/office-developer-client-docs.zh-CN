---
title: IMAPIPropSaveChanges
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.SaveChanges
api_type:
- COM
ms.assetid: 864dbc3e-2039-435a-a279-385d79d1d13f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2c8244180a5cafedc887fa72f36f233fb5084f79
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316630"
---
# <a name="imapipropsavechanges"></a>IMAPIProp::SaveChanges

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
永久更改自上次保存操作以来对对象所做的更改。 
  
```cpp
HRESULT SaveChanges(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制调用 **IMAPIProp：：SaveChanges** 方法时对象发生的情况的标志位掩码。 可以设置以下标志： 
    
NON_EMS_XP_SAVE
  
> 指示邮件尚未从邮件Microsoft Exchange Server。 此标志应该与 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法和 ITEMPROC_FORCE 标志结合使用，以向 PST 存储指示在个人文件夹文件 (PST) 存储通知任何侦听客户端邮件已到达之前，邮件符合规则处理条件。 此规则处理仅适用于在非 Exchange Server 服务器上使用[IMAPIFolder：：CreateMessage](imapifolder-createmessage.md)创建的新邮件，在这种情况下，Exchange Server 已经处理了邮件的规则。 
    
FORCE_SAVE 
  
> 更改应写入对象，覆盖之前对该对象所做的更改，并且应关闭该对象。 必须设置读/写权限，操作才能成功。 在FORCE_SAVE **调用 SaveChanges** 后，使用 MAPI_E_OBJECT_CHANGED。 
    
KEEP_OPEN_READONLY 
  
> 应提交更改，并且对象应保持打开状态供读取。 不会进行任何其他更改。 
    
KEEP_OPEN_READWRITE 
  
> 应提交更改，并且对象应保持打开状态，以授予读/写权限。 此标志通常在首次打开对象时设置，以授予读/写权限。 允许对对象进行后续更改。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **SaveChanges** 在完全提交更改之前成功返回。 
    
SPAMFILTER_ONSAVE
  
> 对正在保存的邮件启用垃圾邮件筛选。 垃圾邮件筛选支持只有在发件人的电子邮件地址类型为简单邮件传输协议 (SMTP) 且正在将邮件保存到个人文件夹文件 (PST) 存储区的情况下可用。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 更改的承诺已成功。
    
MAPI_E_NO_ACCESS 
  
> **如果设置了只读权限，SaveChanges** 无法保持该对象为只读权限;如果KEEP_OPEN_READONLY，则保持对象的读/写KEEP_OPEN_READWRITE权限。 不提交任何更改。 
    
MAPI_E_OBJECT_CHANGED 
  
> 对象自打开后已发生更改。
    
MAPI_E_OBJECT_DELETED 
  
> 对象自打开后即被删除。
    
## <a name="remarks"></a>备注

**IMAPIProp：：SaveChanges** 方法对支持处理事务模型的对象（如邮件、附件、通讯簿容器和消息用户对象）进行永久性属性更改。 不支持事务的对象（如文件夹、邮件存储和配置文件部分）会立即永久更改。 无需调用 **SaveChanges。** 
  
由于在保存所有属性之前，服务提供商不需要为对象生成条目标识符，因此对象的 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性在 **调用 SaveChanges** 方法之前可能不可用。 某些提供程序会等到 **saveChanges** KEEP_OPEN_READONLY设置该标记。 KEEP_OPEN_READONLY指示在当前调用中保存的更改将是对对象进行的最后一次更改。 
  
某些邮件存储实现不会在文件夹中显示新创建的邮件，除非客户端使用 **SaveChanges** 保存邮件更改，然后使用 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) 方法释放邮件对象。 此外，在调用 **SaveChanges** **之前，** 某些对象实现无法为新创建的对象生成 PR_ENTRYID 属性，而有些对象实现只有在使用 _ulFlags_ 中设置的 KEEP_OPEN_READONLY 调用 **SaveChanges** 之后才能这样做。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果收到KEEP_OPEN_READONLY标记，可以选择将对象的访问权保留为可读/写。 但是，传递对象标记时，提供程序绝不会使对象KEEP_OPEN_READWRITE只读状态。
  
当客户端将多个附件保存到多个邮件时，它会调用每个附件和每封邮件的 **SaveChanges** 方法。 通常，客户端MAPI_DEFERRED_ERRORS每个调用（最后一个除外）的呼叫。 可以在上一次调用或之前调用时返回错误。 甚至可以忽略标志。 
  
如果将 KEEP_OPEN_READWRITE 或 KEEP_OPEN_READONLY 设置为 MAPI_DEFERRED_ERRORS，可以忽略错误延迟请求。 如果未MAPI_DEFERRED_ERRORS  _ulFlags_ 中设置，则可能会为 **SaveChanges** 调用返回之前延迟的错误之一。 
  
远程传输提供程序是否提供此方法的功能实现是可选的，具体取决于实现中的其他设计选择。 如果实现此方法，请根据此处的文档执行。 由于不处理文件夹对象和状态对象，因此远程传输提供程序的 **SaveChanges** 实现至少必须返回 S_OK而不实际执行任何工作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果客户端传递KEEP_OPEN_READONLY，调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法，然后再次调用 **SaveChanges，** 则同一实现可能会失败。 
  
从MAPI_E_NO_ACCESS设置的调用接收KEEP_OPEN_READWRITE，您将继续具有该对象的读/写权限。 可以再次 **调用 SaveChanges，** 将 KEEP_OPEN_READONLY 标志或没有标志与KEEP_OPEN_SUFFIX。 
  
提供程序是否支持KEEP_OPEN_READWRITE取决于提供程序的实现。 
  
若要指示 **SaveChanges** 之后对对象进行的唯一调用是 **IUnknown：：Release，** 请为  _ulFlags_ 参数设置任何标志。 **SaveChanges** 中的错误指示无法永久更改挂起的更改。 不同的提供程序处理 **SaveChanges 调用上缺少** 标志的方式不同。 某些提供程序对此状态视为与KEEP_OPEN_READONLY;其他提供程序将其解释为KEEP_OPEN_READWRITE。 当其他提供程序在 **SaveChanges** 调用上未接收标志时，会关闭该对象。 
  
某些属性（通常为计算的属性）在调用 **SaveChanges（** 在某些情况下为 **Release）** 之前无法处理。
  
进行批量更改（如将附件保存到多个邮件）时，通过设置  _ulFlags_ 中的 MAPI_DEFERRED_ERRORS 标志来延迟错误处理。 如果将多个附件保存到多个邮件，请分别调用一个 **SaveChanges** 和每个邮件一个 **SaveChanges。** 设置每个MAPI_DEFERRED_ERRORS呼叫以及除最后一个附件呼叫之外的所有邮件的附件呼叫标记。 
  
如果 **SaveChanges** 返回MAPI_E_OBJECT_CHANGED，请检查原始对象是否已修改。 如果是，则警告用户，用户可以请求更改覆盖以前的更改或将对象保存到其他位置。 如果原始对象已删除，请警告用户让他们有机会将该对象保存到其他位置。 
  
不能在 **已删除的** 已打开FORCE_SAVE上调用具有 FORCE_SAVE 标志的 SaveChanges。 
  
如果 **SaveChanges** 返回错误，则不管  _ulFlags_ 参数中设置的标志如何，要保存其更改的对象都将保持打开状态。 
  
> [!IMPORTANT]
> _ulFlags_ NON_EMS_XP_SAVE和 SPAMFILTER_ONSAVE可能未在当前具有的可下载头文件中定义，在这种情况下，您可以使用以下值将其添加到代码中：>`#define SPAMFILTER_ONSAVE ((ULONG) 0x00000080)`>  `#define NON_EMS_XP_SAVE ((ULONG) 0x00001000)`
  
有关详细信息，请参阅保存 [MAPI 属性](saving-mapi-properties.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SetProps](imapiprop-setprops.md)
  
[PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[保存 MAPI 属性](saving-mapi-properties.md)

