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
  
使自上次保存操作后对对象进行的任何更改成为永久性的。 
  
```cpp
HRESULT SaveChanges(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时标志的位掩码, 用于控制在调用**IMAPIProp:: SaveChanges**方法时对对象所发生的操作。 可以设置以下标志: 
    
NON_EMS_XP_SAVE
  
> 指示邮件尚未从 Microsoft Exchange Server 传递。 应将此标志与[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法和 ITEMPROC_FORCE 标志结合使用, 以向 PST 存储中指明邮件是否符合规则处理规则, 然后再将个人文件夹文件 (PST) 存储通知任何侦听客户端邮件已到达。 此规则处理仅适用于在不是 Exchange 服务器的服务器上使用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)创建的新邮件, 在这种情况下, Exchange server 可能已经处理了邮件的规则。 
    
FORCE_SAVE 
  
> 应将更改写入对象, 覆盖对对象所做的任何以前的更改, 并且应关闭该对象。 必须设置读/写权限, 才能成功执行此操作。 在对**SaveChanges**返回的上一次调用后使用 FORCE_SAVE 标志 MAPI_E_OBJECT_CHANGED。 
    
KEEP_OPEN_READONLY 
  
> 应提交更改, 并将对象保持打开状态以供阅读。 不会进行其他更改。 
    
KEEP_OPEN_READWRITE 
  
> 应提交更改, 应将该对象保持打开状态以进行读/写权限。 在首次打开对象以进行读/写权限时, 通常会设置此标志。 允许对该对象进行后续更改。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许**SaveChanges**成功返回, 可能在更改完全提交之前。 
    
SPAMFILTER_ONSAVE
  
> 对要保存的邮件启用垃圾邮件筛选。 垃圾邮件筛选支持只有在发件人的电子邮件地址类型为简单邮件传输协议 (SMTP) 且正在将邮件保存到个人文件夹文件 (PST) 存储区的情况下可用。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 更改的承诺已成功完成。
    
MAPI_E_NO_ACCESS 
  
> 如果设置了 KEEP_OPEN_READONLY, 则**SaveChanges**无法保持打开对象以进行只读权限, 如果设置了 KEEP_OPEN_READWRITE, 则不能读取/写入权限。 不提交任何更改。 
    
MAPI_E_OBJECT_CHANGED 
  
> 对象在打开后已更改。
    
MAPI_E_OBJECT_DELETED 
  
> 对象已被删除, 因为它已被打开。
    
## <a name="remarks"></a>注解

对于支持处理的事务模型的对象, **IMAPIProp:: SaveChanges**方法会永久更改属性, 例如邮件、附件、通讯簿容器和邮件用户对象。 不支持事务的对象 (如文件夹、邮件存储区和配置文件节) 会立即永久更改。 不需要对**SaveChanges**的调用。 
  
由于在保存所有属性之前, 服务提供程序不一定要为其对象生成条目标识符, 因此对象的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性在其**SaveChanges**方法后面可能不可用已调用。 有些提供程序会等到在**SaveChanges**调用上设置 KEEP_OPEN_READONLY 标志。 KEEP_OPEN_READONLY 指示要在当前调用中保存的更改是将对该对象进行的最后一处更改。 
  
在客户端通过使用**SaveChanges**保存邮件更改并使用[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法释放 message 对象之前, 某些邮件存储实现不会在文件夹中显示新创建的邮件。 此外, 在调用**savechanges**之前, 某些对象实现无法为新创建的对象生成**PR_ENTRYID**属性, 并且某些对象实现只有在使用 KEEP_OPEN_READONLY 调用**savechanges**之后才能为新创建的对象生成该属性。在_ulFlags_中设置。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果您收到 KEEP_OPEN_READONLY 标志, 则可以选择将对象的访问保留为读/写。 但是, 在传递 KEEP_OPEN_READWRITE 标志时, 提供程序不能使对象处于只读状态。
  
当客户端将多个附件保存到多个邮件中时, 它会为每个附件和每个邮件调用**SaveChanges**方法。 通常, 客户端会为这些呼叫中的每个调用 (最后一个除外) 设置 MAPI_DEFERRED_ERRORS。 您可以使用上一次调用或更早的调用返回错误。 甚至可以忽略该标志。 
  
如果 KEEP_OPEN_READWRITE 或 KEEP_OPEN_READONLY 与 MAPI_DEFERRED_ERRORS 一起设置, 则可以忽略错误延期请求。 如果_ulFlags_中未设置 MAPI_DEFERRED_ERRORS, 则可以为**SaveChanges**调用返回以前延迟的错误之一。 
  
远程传输提供程序是否提供此方法的功能实现是可选的, 并取决于实现中的其他设计选择。 如果您实现此方法, 请根据此处的文档执行此操作。 由于不会对 folder 对象和 status 对象进行事务处理, 因此, 至少远程传输提供程序的**SaveChanges**实现必须返回 S_OK, 而不实际执行任何工作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果客户端传递 KEEP_OPEN_READONLY, 则调用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法, 然后再次调用**SaveChanges** , 相同的实现可能会失败。 
  
从设置 KEEP_OPEN_READWRITE 的呼叫中接收 MAPI_E_NO_ACCESS 之后, 您将继续拥有对该对象的读/写权限。 您可以再次调用**SaveChanges** , 将 KEEP_OPEN_READONLY 标志或没有标志传递给 KEEP_OPEN_SUFFIX。 
  
提供程序是否支持 KEEP_OPEN_READWRITE 标志取决于提供程序的实现。 
  
若要指示在**SaveChanges**为 IUnknown 之后对对象进行的唯一调用 **:: Release**, 请为_ulFlags_参数设置无标志。 **SaveChanges**中的错误指示它无法使挂起的更改成为永久更改。 不同的提供程序以不同的方式处理**SaveChanges**调用上缺少的标志。 某些提供程序将此状态视为与 KEEP_OPEN_READONLY 相同;其他提供程序会将其解释为 KEEP_OPEN_READWRITE。 当其他提供程序在**SaveChanges**调用上未收到标志时, 仍会关闭该对象。 
  
某些属性 (通常是计算属性) 在您调用**SaveChanges**和 (在某些情况下)**发布**之前无法处理。
  
当您进行批量更改 (如将附件保存到多封邮件中) 时, 通过在_ulFlags_中设置 MAPI_DEFERRED_ERRORS 标志来推迟错误处理。 如果将多个附件保存到多封邮件中, 则对每个附件进行一次**savechanges**调用, 并对每封邮件执行一次**savechanges**调用。 为每个附件呼叫和除最后一个邮件之外的所有邮件设置 MAPI_DEFERRED_ERRORS 标志。 
  
如果**SaveChanges**返回 MAPI_E_OBJECT_CHANGED, 请检查原始对象是否已被修改。 如果是这样, 则向用户发出警告, 用户可以请求所做的更改覆盖以前的更改, 或将对象保存到其他位置。 如果原始对象已被删除, 则向用户发出警告, 让他们有机会将该对象保存到另一个位置。 
  
您无法在已删除的打开对象上使用 FORCE_SAVE 标志调用**SaveChanges** 。 
  
如果**SaveChanges**返回错误, 则无论_ulFlags_参数中设置了何种标志, 要保存其更改的对象仍保持打开状态。 
  
> [!IMPORTANT]
> _ulFlags_ NON_EMS_XP_SAVE 和 SPAMFILTER_ONSAVE 可能不是在您当前拥有的可下载头文件中定义的, 在这种情况下, 您可以使用以下值将其添加到代码中: >`#define SPAMFILTER_ONSAVE ((ULONG) 0x00000080)`>  `#define NON_EMS_XP_SAVE ((ULONG) 0x00001000)`
  
有关详细信息, 请参阅[保存 MAPI 属性](saving-mapi-properties.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SetProps](imapiprop-setprops.md)
  
[PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[保存 MAPI 属性](saving-mapi-properties.md)

