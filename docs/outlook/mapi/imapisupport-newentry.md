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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ae2a19d556fc9819312ce822f9347edcd6edc0d6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775630"
---
# <a name="imapisupportnewentry"></a>IMAPISupport::NewEntry

  
  
**适用于**： Outlook 
  
直接到通讯簿容器或传出邮件的收件人列表中添加一个新收件人。
  
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
  
> [in]对话框中的父窗口的句柄。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _cbEIDContainer_
  
> [in]在_lpEIDContainer_参数指向的项标识符的字节数。 
    
 _lpEIDContainer_
  
> [in]指向容器接收新条目的项标识符的指针。 如果_cbEIDContainer_为 0，那么_lpEIDContainer_为 NULL， **NewEntry**创建是相同的类型，如调用[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)方法生成一个一次性条目标识符。 
    
 _cbEIDNewEntryTpl_
  
> [in]在_lpEIDNewEntryTpl_参数指向的项标识符的字节数。 
    
 _lpEIDNewEntryTpl_
  
> [in]指向要用于创建新项的模板的项标识符的指针。 如果_cbEIDNewEntryTpl_为 0，那么_lpEIDNewEntryTpl_为 NULL，则**NewEntry**显示一个对话框，使用户能够从模板用于添加新条目的列表中选择。 
    
 _lpcbEIDNewEntry_
  
> [输出]一个指向_lppEIDNewEntry_参数指向该条目标识符中的字节数。 
    
 _lppEIDNewEntry_
  
> [输出]指向新创建的项的项标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建新条目。
    
## <a name="remarks"></a>说明

对于通讯簿提供程序支持对象实现**IMAPISupport::NewEntry**方法。 通讯簿提供程序调用**NewEntry**创建新的通讯簿条目，直接将容器添加或要用于传出邮件地址。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果您希望新条目添加到特定的容器，设置为容器的项标识符和_cbEIDContainer_中的项标识符的字节数为_lpEIDContainer_ 。 
  
如果您希望添加到的传出邮件的收件人列表的新项，设置为空，并且为 0 _cbEIDContainer_ _lpEIDContainer_ 。 
  
如果您想要允许客户端应用程序选择项的类型的用户创建，传递 0 _cbEIDNewEntryTpl_和_lpEIDNewEntryTpl_中的 NULL。 **NewEntry**显示 MAPI 一次性表，MAPI 和每个会话中的地址簿提供程序支持的模板的列表。 每个模板可以创建一个或多个地址类型的收件人条目。 
  
如果您想要保留的新条目的项标识符，在_lpcbEIDNewEntry_和_lppEIDNewEntry_参数中传递有效的指针。 您负责完与其通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放此条目标识符。 
  
若要使用特定模板可修改容器中添加一个新项，请使用以下过程：
  
1. 调用[IMAPISupport::OpenEntry](imapisupport-openentry.md)方法以打开目标容器中，并将_lpEntryID_参数设置为容器的项标识符。 
    
2. 调用目标容器[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法，并将**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) _ulPropTag_参数和_lpiid_参数设置为 IID_IMAPITable。 容器将返回一次性表，其中列出的所有模板它支持创建新条目。 
    
3. 检索表示您想要创建的项的特定类型的模板的行。 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 列指示由模板支持的地址类型。 
    
4. 调用**IMAPISupport::NewEntry**并_lpEIDNewEntryTpl_参数设置为所选模板的项标识符。 项标识符是一次性的表中的模板的行中的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。 传递 0 _cbEIDContainer_和_lpEIDContainer_中的 NULL。 如果您想要保留的新条目的项标识符，请在_lppEIDNewEntry_参数中传递一个有效的指针。 
    
## <a name="see-also"></a>另请参阅



[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPISupport::OpenEntry](imapisupport-openentry.md)
  
[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

