---
title: IAddrBookNewEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.NewEntry
api_type:
- COM
ms.assetid: 8d2d786b-e621-456d-b087-3373df6f8ac5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 285da82d143524d2b2cf73ed3e5f1e3aeef6f9b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405098"
---
# <a name="iaddrbooknewentry"></a>IAddrBook::NewEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将新的收件人添加到通讯簿容器或传出邮件的收件人列表中。
  
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
  
> 实时标志的位掩码, 用于控制所使用文本的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _cbEIDContainer_
  
> 实时条目标识符中由_lpEIDContainer_参数指向的字节数。 
    
 _lpEIDContainer_
  
> 实时一个指针, 指向要在其中添加新收件人的容器的条目标识符。 如果_cbEIDContainer_参数为零, **NewEntry**方法将返回收件人条目标识符和模板列表, 就像调用了[IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md)方法一样。 
    
 _cbEIDNewEntryTpl_
  
> 实时条目标识符中由_lpEIDNewEntryTpl_参数指向的字节数。 
    
 _lpEIDNewEntryTpl_
  
> 实时指向将用于创建新收件人的一次性模板的指针。 如果_cbEIDNewEntryTpl_为零且_lpEIDNewEntryTpl_为 NULL, 则**NewEntry**将显示一个对话框, 用户可以从该对话框中选择用于添加新条目的模板列表。 
    
 _lpcbEIDNewEntry_
  
> 排除指向条目标识符中由_lppEIDNewEntry_参数指向的字节计数的指针。 
    
 _lppEIDNewEntry_
  
> 排除指向新收件人的条目标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建新的通讯簿条目。
    
## <a name="remarks"></a>说明

**NewEntry**方法创建一个新的通讯簿条目, 以将其直接添加到容器中或用于处理传出邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果要将新项添加到特定容器, 请将_lpEIDContainer_的条目标识符和_cbEIDContainer_设置为条目标识符中的字节数。 
  
如果要将新条目添加到传出邮件的收件人列表中, 请将_lpEIDContainer_设置为 NULL, 并将_cbEIDContainer_设置为零。 
  
如果要允许客户端应用程序的用户选择要创建的条目的类型, 请在_lpEIDNewEntryTpl_中传递_cbEIDNewEntryTpl_和 NULL 中的零。 **NewEntry**方法显示 mapi 的一次性表、mapi 支持的模板列表以及会话中的每个通讯簿提供程序。 每个模板都可以为一个或多个地址类型创建收件人条目。 
  
如果要保留新条目的条目标识符, 请在_lpcbEIDNewEntry_和_lppEIDNewEntry_参数中传递有效的指针。 通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 您负责在完成此条目标识符后释放此条目标识符。 
  
若要使用特定模板将新条目添加到可修改容器中, 请使用以下过程:
  
1. 调用[IMAPISession:: OpenEntry](imapisession-openentry.md)方法打开目标容器, 并将_lpEntryID_参数设置为容器的条目标识符。 
    
2. 调用目标容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 并将_ulPropTag_参数设置为**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)), 并将_lpiid_参数设置为 IID_IMAPITable。 容器将返回一个一次性表格, 其中列出了创建新条目所支持的所有模板。 
    
3. 检索表示要创建的特定类型的条目的模板的行。 " **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))" 列指示模板支持的地址类型。
    
4. 调用**NewEntry**方法, 并将_lpEIDNewEntryTpl_设置为选定模板的条目标识符。 条目标识符将是来自一次性表中的模板行的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。 在_lpEIDContainer_中传递_cbEIDContainer_和 NULL 中的零。 如果要保留新条目的条目标识符, 请在_lppEIDNewEntry_参数中传递有效的指针。 
    
## <a name="see-also"></a>另请参阅



[IAddrBook::OpenEntry](iaddrbook-openentry.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

