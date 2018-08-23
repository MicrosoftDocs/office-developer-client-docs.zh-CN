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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c12750b7899403e62b9c1603615e9fd6caa95eca
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569524"
---
# <a name="imapipropsavechanges"></a>IMAPIProp::SaveChanges

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
使永久自上次保存操作对对象进行的任何更改。 
  
```cpp
HRESULT SaveChanges(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，用于控制调用**IMAPIProp::SaveChanges**方法时，该对象会发生什么情况。 可以设置以下标志： 
    
NON_EMS_XP_SAVE
  
> 指示邮件尚未传递从 Microsoft Exchange Server。 此标志应结合使用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法和 ITEMPROC_FORCE 标志，以指示到 PST 存储符合条件的邮件规则处理之前的个人文件夹文件 (PST) 存储通知任何邮件已到达的侦听客户端。 处理仅适用于新创建的邮件使用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)不是 Exchange 服务器，这种情况下的服务器上 Exchange Server 此规则将已处理邮件的规则。 
    
FORCE_SAVE 
  
> 更改应写入替代对该对象，所做的任何以前更改的对象，以及应关闭该对象。 若要成功执行此操作，必须设置读/写权限。 **SaveChanges**为以前的呼叫返回 MAPI_E_OBJECT_CHANGED 之后使用 FORCE_SAVE 标志。 
    
KEEP_OPEN_READONLY 
  
> 应将更改提交和对象应保持打开以进行读取。 将不进行任何其他更改。 
    
KEEP_OPEN_READWRITE 
  
> 应将更改提交和对象应保持打开读/写权限。 读/写权限的首次打开对象时，通常是设置此标志。 允许对对象的后续更改。 
    
MAPI_DEFERRED_ERRORS 
  
> 允许**SaveChanges**返回成功，原因可能是完全提交更改之前。 
    
SPAMFILTER_ONSAVE
  
> 启用垃圾邮件筛选正在保存一条消息。 只有当发件人的电子邮件地址类型为简单邮件传输协议 (SMTP)，并且将存储个人文件夹文件 (PST) 用于保存邮件的垃圾邮件筛选支持可用。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 更改的承诺成功。
    
MAPI_E_NO_ACCESS 
  
> **SaveChanges**无法该对象保持打开状态的只读权限 KEEP_OPEN_READONLY 是否集或读/写权限如果 KEEP_OPEN_READWRITE 设置。 无更改被提交。 
    
MAPI_E_OBJECT_CHANGED 
  
> 对象已更改，因为它打开的。
    
MAPI_E_OBJECT_DELETED 
  
> 对象已被删除，因为它打开的。
    
## <a name="remarks"></a>注解

**IMAPIProp::SaveChanges**方法使属性更改永久支持处理，如邮件、 附件、 通讯簿容器和邮件用户对象的事务模型的对象。 不支持事务，如文件夹、 消息存储和配置文件节的对象进行的更改永久立即。 不需要调用**SaveChanges**是必需的。 
  
服务提供商不需要生成其对象的项标识符已保存了所有属性之前，因为对象的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性可能不可用直到后其**SaveChanges**方法调用了。 某些提供程序等待，直到 KEEP_OPEN_READONLY 标志设置**SaveChanges**呼叫。 KEEP_OPEN_READONLY 指示保存在当前呼叫中的更改将最后一个将对对象所做的更改。 
  
某些消息存储实现执行操作不显示新创建的文件夹中的邮件客户端之前保存邮件使用**SaveChanges**更改，并使用[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法释放消息对象。 此外，某些对象实现无法生成新创建的对象，直到**PR_ENTRYID**属性后已调用**SaveChanges** ，并且某些可以仅在**SaveChanges**已由使用 KEEP_OPEN_READONLY 调用之后执行此操作在_ulFlags_中设置。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果您收到 KEEP_OPEN_READONLY 标志，您可以离开以读/写对象的访问。 但是，提供程序可以从不使对象处于只读状态时传递 KEEP_OPEN_READWRITE 标志。
  
时客户端多个将附件保存到多个邮件，每个附件和每个邮件将调用的**SaveChanges**方法。 通常客户端将为每个这些呼叫的最后一个除设置 MAPI_DEFERRED_ERRORS。 您可以返回错误是与早期的呼叫的最后一个呼叫。 您甚至可以忽略标志。 
  
如果 KEEP_OPEN_READWRITE 或 KEEP_OPEN_READONLY MAPI_DEFERRED_ERRORS 一起设置，可以忽略错误延期请求。 如果_ulFlags_中未设置 MAPI_DEFERRED_ERRORS，之前延迟的错误之一可以返回**SaveChanges**呼叫。 
  
远程传输提供程序是否提供功能齐全的实现此方法是可选的取决于您的实现中其他设计选项。 如果实现此方法，请根据下面的文档。 文件夹对象和状态对象不事务处理，因为至少远程传输提供程序的实现的**SaveChanges**必须返回 S_OK 而不实际执行任何工作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果客户端将传递 KEEP_OPEN_READONLY 和调用[IMAPIProp::SetProps](imapiprop-setprops.md)方法，然后再次调用**SaveChanges** ，相同的实现可能会失败。 
  
从呼叫接收 MAPI_E_NO_ACCESS 之后在其中将设置 KEEP_OPEN_READWRITE，您将继续具有对对象的读/写权限。 您可以调用**SaveChanges**再次，传递 KEEP_OPEN_READONLY 标志或 KEEP_OPEN_SUFFIX 与任何标志。 
  
提供程序是否支持 KEEP_OPEN_READWRITE 标志取决于提供程序的实现。 
  
若要指示仅在**SaveChanges**后进行的对象上呼叫**IUnknown::Release**，请设置_ulFlags_参数的任何标志。 从**SaveChanges**错误指示，它无法使待处理的更改永久。 不同的提供程序以不同方式处理标志**SaveChanges**呼叫不存在。 某些提供程序视为此状态相同 KEEP_OPEN_READONLY;其他提供程序将其解释 KEEP_OPEN_READWRITE 相同。 仍然其他提供程序关闭该对象时不会收到上**SaveChanges**呼叫的标志。 
  
在您调用**SaveChanges**之前以及在某些情况下，**发布**无法处理某些属性，通常计算属性。
  
当您进行批量更改，如将附件保存到多个邮件时延迟处理通过_ulFlags_中设置 MAPI_DEFERRED_ERRORS 标志的错误。 如果保存多个附件给多个邮件，使一个**SaveChanges**对每个附件的调用和一个**SaveChanges**调用每条消息。 设置 MAPI_DEFERRED_ERRORS 标志为每个附件呼叫和最后一个除外的所有邮件。 
  
如果**SaveChanges**返回 MAPI_E_OBJECT_CHANGED，检查是否已修改的原始对象。 如果是这样，警告的用户，也可以请求所做的更改覆盖以前的更改，或保存在其他地方的对象。 如果原始对象已被删除，警告用户要为其提供的机会将对象保存在另一个位置。 
  
不能与上打开的对象已删除的 FORCE_SAVE 标志调用**SaveChanges** 。 
  
如果**SaveChanges**返回一个错误，其更改已保存保持对象打开，无论设置_ulFlags_参数中的标志。 
  
> [!IMPORTANT]
> _UlFlags_ NON_EMS_XP_SAVE 和 SPAMFILTER_ONSAVE 可能未定义当前具有可下载头文件中，在这种情况下您可以将其添加到代码中使用以下值： >`#define SPAMFILTER_ONSAVE ((ULONG) 0x00000080)`>  `#define NON_EMS_XP_SAVE ((ULONG) 0x00001000)`
  
有关详细信息，请参阅[保存 MAPI 属性](saving-mapi-properties.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::SetProps](imapiprop-setprops.md)
  
[PidTagEntryId 规范属性](pidtagentryid-canonical-property.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[保存 MAPI 属性](saving-mapi-properties.md)

