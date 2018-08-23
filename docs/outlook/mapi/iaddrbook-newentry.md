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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: eaf472a380acd62cddb2c20c35335ccb1e2ce07f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585855"
---
# <a name="iaddrbooknewentry"></a>IAddrBook::NewEntry

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
将一个新收件人添加到通讯簿容器或传出邮件的收件人列表。
  
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
  
> [in]对话框中的父窗口句柄。
    
 _ulFlags_
  
> [in]位掩码的标志的控制使用的文本的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _cbEIDContainer_
  
> [in]在_lpEIDContainer_参数指向的项标识符的字节数。 
    
 _lpEIDContainer_
  
> [in]指向新收件人的要添加的容器的项标识符的指针。 如果_cbEIDContainer_参数为零， **NewEntry**方法就会返回一个收件人的项标识符和模板的列表就好像调用[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)方法。 
    
 _cbEIDNewEntryTpl_
  
> [in]在_lpEIDNewEntryTpl_参数指向的项标识符的字节数。 
    
 _lpEIDNewEntryTpl_
  
> [in]一个指向将用于创建新收件人的一次性模板。 如果_cbEIDNewEntryTpl_为零，并且_lpEIDNewEntryTpl_为 NULL， **NewEntry**将显示一个对话框，与用户可以选择从列表中添加新项的模板。 
    
 _lpcbEIDNewEntry_
  
> [输出]一个指向_lppEIDNewEntry_参数指向该条目标识符中的字节数。 
    
 _lppEIDNewEntry_
  
> [输出]为指向新收件人的项标识符的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建新的通讯簿条目。
    
## <a name="remarks"></a>注解

**NewEntry**方法创建新通讯簿条目，直接将容器添加或要用于传出邮件地址。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果您希望新条目添加到特定的容器，设置为容器的项标识符和_cbEIDContainer_中的项标识符的字节数为_lpEIDContainer_ 。 
  
如果您希望添加到的传出邮件的收件人列表的新项，设置为空，并且为零的_cbEIDContainer_ _lpEIDContainer_ 。 
  
如果您想要允许客户端应用程序选择项的类型的用户创建，传递零_cbEIDNewEntryTpl_在和中_lpEIDNewEntryTpl_NULL。 **NewEntry**方法显示 MAPI 一次性表，通过 MAPI 和每个通讯簿提供程序支持会话中的模板的列表。 每个模板可以创建一个或多个地址类型的收件人条目。 
  
如果您想要保留的新条目的项标识符，在_lpcbEIDNewEntry_和_lppEIDNewEntry_参数中传递有效的指针。 您负责完与其通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放此条目标识符。 
  
若要使用特定模板可修改容器中添加一个新项，请使用以下过程：
  
1. 调用[IMAPISession::OpenEntry](imapisession-openentry.md)方法以打开目标容器中，并将_lpEntryID_参数设置为容器的项标识符。 
    
2. 调用目标容器[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法，并将**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) _ulPropTag_参数和_lpiid_参数设置为 IID_IMAPITable。 容器将返回一个一次性表，列出所有它支持用于创建新条目的模板。 
    
3. 检索表示您想要创建的项的特定类型的模板的行。 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 列指示由模板支持的地址类型。
    
4. 调用**NewEntry**方法，并将_lpEIDNewEntryTpl_设置为所选模板的项标识符。 项标识符将是一次性的表中的模板的行中的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。 传递零_cbEIDContainer_在和中_lpEIDContainer_NULL。 如果您想要保留的新条目的项标识符，请在_lppEIDNewEntry_参数中传递一个有效的指针。 
    
## <a name="see-also"></a>另请参阅



[IAddrBook::OpenEntry](iaddrbook-openentry.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

