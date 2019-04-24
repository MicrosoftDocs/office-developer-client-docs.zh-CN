---
title: IABContainerCopyEntries
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABContainer.CopyEntries
api_type:
- COM
ms.assetid: 4e775228-5ceb-4002-9b68-999fb5889b86
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ddb730ed92db4c8d281e7c8d5d9b18bc44505598
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346394"
---
# <a name="iabcontainercopyentries"></a>IABContainer::CopyEntries

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
复制一个或多个条目, 通常是邮件用户或通讯组列表。
  
```cpp
HRESULT CopyEntries(
  LPENTRYLIST lpEntries,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpEntries_
  
> 实时一个指针, 指向[ENTRYLIST](entrylist.md)结构的数组, 其中包含要复制的条目的条目标识符。 
    
 _ulUIParam_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。 如果在_ulFlags_参数中设置了 AB_NO_DIALOG 标志, 则_ulUIParam_参数必须为零。 
    
 _lpProgress_
  
> 实时指向显示进度指示器的进度对象的指针或 NULL。 如果_lpProgress_为 NULL, 则应使用 MAPI 通过[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)方法提供的进度对象显示进度指示器。 如果在_ulFlags_中设置了 AB_NO_DIALOG 标志, 则将忽略_lpProgress_参数。
    
 _ulFlags_
  
> 实时用于控制如何执行复制操作的标志的位掩码。 可以设置以下标志:
    
AB_NO_DIALOG 
  
> 禁止显示进度指示器。 如果未设置此标志, 则显示一个进度指示器。
    
CREATE_CHECK_DUP_LOOSE 
  
> 指示应执行的是松散级别的重复项检查。 松散重复项检查的实现是特定于提供程序的。 例如, 提供程序可以将松散匹配定义为任意两个具有相同显示名称的条目。
    
CREATE_CHECK_DUP_STRICT 
  
> 指示应执行严格的重复项检查级别。 严格的重复项检查实现是特定于提供程序的。 例如, 提供程序可以将一个严格的匹配定义为两个具有相同的显示名称和邮件地址的条目。
    
CREATE_REPLACE 
  
> 指示一个新的条目应替换现有的条目, 如果确定两者是重复的。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 复制操作成功。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 复制操作全部成功, 但无法复制一个或多个条目。 返回此值时, 应以成功的方式处理该调用。 若要测试此值, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IABContainer:: CopyEntries**方法从同一个容器或不同的容器复制条目。 对**CopyEntries**的调用在功能上等效于为要复制的每个条目进行以下调用: 
  
1. 用于创建新条目的[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法。 
    
2. [IMAPIProp:: GetProps](imapiprop-getprops.md)方法可读取要复制的项的属性。 
    
3. [IMAPIProp:: SetProps](imapiprop-setprops.md)方法将属性写入新条目。 
    
4. 新条目的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法来执行保存。 
    
5. 新条目的[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx)方法, 用于释放容器的引用。 
    
## <a name="notes-to-implementers"></a>针对实现者的说明

支持**IABContainer:: CopyEntries**方法的所有容器都必须是可修改的。 在其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置容器的 AB_MODIFIABLE 标志, 以指示它是可修改的。 
  
您必须支持所有标志;但是, 这些标志的解释和使用是特定于实现的, 也就是说, 您可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志的语义在实现的上下文中的含义。 如果不能或不确定某个条目是否重复, 则始终允许复制该条目。 
  
如果设置了 CREATE_REPLACE 标志, 无论是否设置了 CREATE_CHECK_DUP_LOOSE 或 CREATE_CHECK_DUP_STRICT 以及条目是否重复, 都始终复制该条目。 
  
如果未设置 CREATE_REPLACE 且 CREATE_CHECK_DUP_STRICT 已设置, 请检查重复项。 如果确定某一项是重复项, 则不要复制该项。 
  
您无需支持 CREATE_REPLACE;不支持 CREATE_REPLACE 意味着您可以安全地忽略它并始终执行复制。 
  
仅当无法复制 nonduplicate 条目时, 才返回警告 MAPI_W_PARTIAL_COMPLETION。 
  
## <a name="notes-to-callers"></a>给调用方的说明

使用 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志向提供程序指明您希望容器执行重复项检查的方式。 如果您需要添加一个条目, 而不考虑它是否重复, 则要么不设置这些标志中的任何一个, 要么设置 CREATE_REPLACE 标志。 CREATE_REPLACE 指示您不介意条目是否重复;您始终希望它替换原始条目。 
  
## <a name="see-also"></a>另请参阅



[ENTRYLIST](entrylist.md)
  
[IABContainer::CreateEntry](iabcontainer-createentry.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)

