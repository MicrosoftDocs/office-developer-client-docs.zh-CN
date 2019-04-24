---
title: IMAPISupportNewEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.NewEntry
api_type:
- COM
ms.assetid: 588d002b-8412-4ab9-9757-04ad89e0a6f8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3468e4a92787e440f230d60ab31f37526fe7d5e8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316639"
---
# <a name="imapisupportnewentry"></a>IMAPISupport::NewEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将新的收件人直接添加到通讯簿容器或传出邮件的收件人列表中。
  
```cpp
HRESULT NewEntry(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG cbEIDContainer,
  LPENTRYID lpEIDContainer,
  ULONG cbEIDNewEntryTpl,
  LPENTRYID lpEIDNewEntryTpl,
  ULONG FAR * lpcbEIDNewEntry,
  LPENTRYID FAR * lppEIDNewEntry
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> 实时对话框的父窗口的句柄。
    
 _ulFlags_
  
> 实时保留必须为零。
    
 _cbEIDContainer_
  
> 实时条目标识符中由_lpEIDContainer_参数指向的字节数。 
    
 _lpEIDContainer_
  
> 实时指向接收新条目的容器的条目标识符的指针。 如果_cbEIDContainer_为 0, 并且_lpEIDContainer_为 NULL, 则**NewEntry**将创建一个与调用[IMAPISupport:: CreateOneOff](imapisupport-createoneoff.md)方法时生成的一次性条目标识符。 
    
 _cbEIDNewEntryTpl_
  
> 实时条目标识符中由_lpEIDNewEntryTpl_参数指向的字节数。 
    
 _lpEIDNewEntryTpl_
  
> 实时指向要用于创建新条目的模板的条目标识符的指针。 如果_cbEIDNewEntryTpl_为 0, 并且_lpEIDNewEntryTpl_为 NULL, 则**NewEntry**将显示一个对话框, 使用户可以从用于添加新条目的模板列表中进行选择。 
    
 _lpcbEIDNewEntry_
  
> 排除指向条目标识符中由_lppEIDNewEntry_参数指向的字节计数的指针。 
    
 _lppEIDNewEntry_
  
> 排除指向新创建条目的条目标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建新条目。
    
## <a name="remarks"></a>注解

为通讯簿提供程序支持对象实现了**IMAPISupport:: NewEntry**方法。 通讯簿提供程序调用**NewEntry**以创建要直接添加到容器中的新通讯簿条目, 或用于处理传出邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果要将新项添加到特定容器, 请将_lpEIDContainer_的条目标识符和_cbEIDContainer_设置为条目标识符中的字节数。 
  
如果要将新条目添加到传出邮件的收件人列表中, 请将_lpEIDContainer_设置为 NULL, 并将_cbEIDContainer_设置为0。 
  
如果要允许客户端应用程序的用户选择要创建的条目的类型, 请在_cbEIDNewEntryTpl_中传递 0, 在_lpEIDNewEntryTpl_中为 NULL。 **NewEntry**显示 mapi 一次性表, 即 mapi 和会话支持中的每个通讯簿提供程序的模板列表。 每个模板都可以为一个或多个地址类型创建收件人条目。 
  
如果要保留新条目的条目标识符, 请在_lpcbEIDNewEntry_和_lppEIDNewEntry_参数中传递有效的指针。 通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 您负责在完成此条目标识符后释放此条目标识符。 
  
若要使用特定模板将新条目添加到可修改容器中, 请使用以下过程:
  
1. 调用[IMAPISupport:: OpenEntry](imapisupport-openentry.md)方法打开目标容器, 并将_lpEntryID_参数设置为容器的条目标识符。 
    
2. 调用目标容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 并将_ulPropTag_参数设置为**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)), 并将_lpiid_参数设置为 IID_IMAPITable。 容器将返回一个一次性表格, 其中列出了创建新条目所支持的所有模板。 
    
3. 检索表示要创建的特定类型的条目的模板的行。 " **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))" 列指示模板支持的地址类型。 
    
4. 调用**IMAPISupport:: NewEntry**并将_lpEIDNewEntryTpl_参数设置为选定模板的条目标识符。 条目标识符是来自一次性表中的模板行的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。 在_lpEIDContainer_中传递_cbEIDContainer_中的0和 NULL。 如果要保留新条目的条目标识符, 请在_lppEIDNewEntry_参数中传递有效的指针。 
    
## <a name="see-also"></a>另请参阅



[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPISupport::OpenEntry](imapisupport-openentry.md)
  
[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

