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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ddb730ed92db4c8d281e7c8d5d9b18bc44505598
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382944"
---
# <a name="iabcontainercopyentries"></a>IABContainer::CopyEntries

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
复制一个或多个条目，通常消息的用户或通讯组列表。
  
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
  
> [in]指向包含要复制的项的项标识符的[ENTRYLIST](entrylist.md)结构数组的指针。 
    
 _ulUIParam_
  
> [in]任何对话框的父窗口或该方法显示的窗口句柄。 _UlUIParam_参数必须为零，如果_ulFlags_参数中设置 AB_NO_DIALOG 标志。 
    
 _lpProgress_
  
> [in]指向显示进度指示器，则为 NULL 的进度对象的指针。 如果_lpProgress_为 NULL，则应使用由 MAPI 提供通过[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)方法的进度对象显示进度指示器。 如果_ulFlags_中设置了 AB_NO_DIALOG 标志，则忽略_lpProgress_参数。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何执行复制操作。 可以设置以下标志：
    
AB_NO_DIALOG 
  
> 禁止显示进度指示器。 如果未设置此标志，将显示进度指示器。
    
CREATE_CHECK_DUP_LOOSE 
  
> 指示应执行的重复项检查松散级别。 提供程序特定的松散重复项检查实现。 例如，提供程序可以定义松散匹配项，如任何具有相同的两个条目的显示名称。
    
CREATE_CHECK_DUP_STRICT 
  
> 指示应执行的重复项检查严格级别。 提供程序特定的严格的重复项检查实现。 例如，提供程序可以定义严格匹配项，如任何具有两个相同的两个条目显示名称和消息地址。
    
CREATE_REPLACE 
  
> 指示是否确定两个是重复项，新条目应替换现有的场。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 复制操作已成功。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 复制操作成功总体上讲，但无法复制一个或多个条目。 返回此值时，应处理呼叫为成功。 若要测试此值，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

**IABContainer::CopyEntries**方法将从同一个容器或其他容器复制条目。 调用**CopyEntries**功能上等效于调用以下为每个要复制的项： 
  
1. 要创建新条目的[IABContainer::CreateEntry](iabcontainer-createentry.md)方法。 
    
2. 要从要复制的项读取属性的[IMAPIProp::GetProps](imapiprop-getprops.md)方法。 
    
3. 要属性写入新条目的[IMAPIProp::SetProps](imapiprop-setprops.md)方法。 
    
4. 新条目的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法执行保存。 
    
5. 新条目的[IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx)方法来释放容器的引用。 
    
## <a name="notes-to-implementers"></a>针对实现者的说明

所有容器都支持**IABContainer::CopyEntries**方法必须都进行修改。 指示可修改其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置您的容器 AB_MODIFIABLE 标志。 
  
您必须支持的所有标志;但是，解释和使用这些标志是实现特定 — 即，您可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志的语义实现的上下文中的含义。 如果您不能或不确定条目是否重复，始终允许要复制的条目。 
  
如果设置了 CREATE_REPLACE 标志，始终复制而不考虑是否设置 CREATE_CHECK_DUP_LOOSE 或 CREATE_CHECK_DUP_STRICT 和条目是否重复的条目。 
  
如果未设置 CREATE_REPLACE 并设置 CREATE_CHECK_DUP_STRICT，检查重复项。 如果条目确定要重复，不复制该条目。 
  
不需要支持 CREATE_REPLACE;不支持 CREATE_REPLACE 意味着，您可以放心地忽略并且始终执行复制。 
  
仅当未复制条目不能复制返回警告 MAPI_W_PARTIAL_COMPLETION。 
  
## <a name="notes-to-callers"></a>给调用方的说明

使用 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志指示到提供程序所需的容器执行重复项检查的方式。 如果您需要具有添加无论它是否是重复的条目，既不设置这些标志任一或设置 CREATE_REPLACE 标志。 CREATE_REPLACE 指示不关心是否条目是重复;希望它始终以替换原始条目。 
  
## <a name="see-also"></a>另请参阅



[ENTRYLIST](entrylist.md)
  
[IABContainer::CreateEntry](iabcontainer-createentry.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)
  
[IABContainer : IMAPIContainer](iabcontainerimapicontainer.md)

