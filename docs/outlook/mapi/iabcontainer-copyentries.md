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
  
复制一个或多个条目，通常为邮件用户或通讯组列表。
  
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
  
> [in]指向包含要复制的条目的条目标识符的 [ENTRYLIST](entrylist.md) 结构的数组的指针。 
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 如果在  _ulFlags_ 参数中设置了 AB_NO_DIALOG 标志，则  _ulUIParam_ 参数必须为零。 
    
 _lpProgress_
  
> [in]指向显示进度指示器的进度对象的指针，或 NULL。 如果  _lpProgress_ 为 NULL，则应该使用 MAPI 通过 [IMAPISupport：:D oProgressDialog](imapisupport-doprogressdialog.md) 方法提供的进度对象来显示进度指示器。 如果在 ulFlags 中设置了 AB_NO_DIALOG 标志，则  _忽略 lpProgress_  _参数_。
    
 _ulFlags_
  
> [in]控制复制操作执行方式的标志的位掩码。 可以设置以下标志：
    
AB_NO_DIALOG 
  
> 禁止显示进度指示器。 如果未设置此标志，则显示进度指示器。
    
CREATE_CHECK_DUP_LOOSE 
  
> 指示应执行松散级别的重复项检查。 松散重复项检查的实现特定于提供程序。 例如，提供程序可以将松散匹配定义为任何两个具有相同的匹配显示名称。
    
CREATE_CHECK_DUP_STRICT 
  
> 指示应执行严格的重复项检查级别。 严格重复项检查的实现特定于提供程序。 例如，提供程序可以将严格匹配定义为任何两个条目，这些条目具有相同的显示名称地址。
    
CREATE_REPLACE 
  
> 指示如果确定两者是重复项，则新条目应替换现有的条目。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 复制操作成功。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 复制操作整体成功，但无法复制一个或多个条目。 返回此值时，应成功处理调用。 若要测试此值，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IABContainer：：CopyEntries** 方法从同一容器或不同容器复制条目。 对 **CopyEntries** 的调用在功能上等效于对要复制的每个条目进行以下调用： 
  
1. 用于 [创建新条目的 IABContainer：：CreateEntry](iabcontainer-createentry.md) 方法。 
    
2. 用于读取要复制的条目中的属性的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法。 
    
3. [用于将属性写入新条目的 IMAPIProp：：SetProps](imapiprop-setprops.md)方法。 
    
4. 要执行保存的新 [条目的 IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。 
    
5. 新条目的 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) 方法，用于释放容器的引用。 
    
## <a name="notes-to-implementers"></a>针对实现者的说明

支持 **IABContainer：：CopyEntries** 方法的所有容器都必须可修改。 使用[PidTagContainerFlags AB_MODIFIABLE PidTagContainerFlags](pidtagcontainerflags-canonical-property.md) PR_CONTAINER_FLAGS (设置容器的) 标志，以指示它是可修改的。  
  
必须支持所有标志;但是，这些标志的解释和使用特定于实现，也就是说，你可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志的语义在实现上下文中的含义。 如果无法确定条目是否是重复项，请始终允许复制该条目。 
  
如果CREATE_REPLACE，则始终复制条目，CREATE_CHECK_DUP_LOOSE或CREATE_CHECK_DUP_STRICT条目是否重复。 
  
如果未CREATE_REPLACE未设置CREATE_CHECK_DUP_STRICT，请检查重复项。 如果某个条目被确定为重复项，则不要复制该条目。 
  
无需支持CREATE_REPLACE;不支持CREATE_REPLACE意味着可以安全地忽略它并始终执行副本。 
  
仅在无法MAPI_W_PARTIAL_COMPLETION重复条目时，才返回警告消息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

使用 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志向提供程序指示您希望容器如何执行重复项检查。 如果需要添加一个条目，无论该条目是否是重复项，请不要设置这些标志中的任一标志或设置CREATE_REPLACE标记。 CREATE_REPLACE表示您不关心条目是否重复;始终希望它替换原始条目。 
  
## <a name="see-also"></a>另请参阅



[ENTRYLIST](entrylist.md)
  
[IABContainer::CreateEntry](iabcontainer-createentry.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)

