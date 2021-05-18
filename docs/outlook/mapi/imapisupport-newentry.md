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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405455"
---
# <a name="imapisupportnewentry"></a>IMAPISupport::NewEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将新收件人直接添加到通讯簿容器或传出邮件的收件人列表。
  
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
  
> [in]对话框父窗口的句柄。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _cbEIDContainer_
  
> [in]  _lpEIDContainer_ 参数指向的条目标识符中的字节计数。 
    
 _lpEIDContainer_
  
> [in]指向容器的条目标识符以接收新条目的指针。 如果  _cbEIDContainer_ 为 0 且  _lpEIDContainer_ 为 NULL， **则 NewEntry** 将创建一个与 [IMAPISupport：：CreateOneOff](imapisupport-createoneoff.md) 方法调用生成的类型相同的一次输入标识符。 
    
 _cbEIDNewEntryTpl_
  
> [in]  _lpEIDNewEntryTpl_ 参数指向的条目标识符中的字节计数。 
    
 _lpEIDNewEntryTpl_
  
> [in]指向要用于创建新条目的模板的条目标识符的指针。 如果  _cbEIDNewEntryTpl_ 为 0 且  _lpEIDNewEntryTpl_ 为 NULL， **则 NewEntry** 将显示一个对话框，使用户能够从模板列表中选择用于添加新条目。 
    
 _lpcbEIDNewEntry_
  
> [out]指向  _lppEIDNewEntry_ 参数指向的条目标识符中的字节计数的指针。 
    
 _lppEIDNewEntry_
  
> [out]指向指向新创建的条目的条目标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建新条目。
    
## <a name="remarks"></a>备注

**为通讯簿提供程序支持对象实现 IMAPISupport：：NewEntry** 方法。 通讯簿提供程序调用 **NewEntry** 以创建要直接添加到容器中或用于处理传出邮件的新通讯簿条目。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果希望将新条目添加到特定容器，将  _lpEIDContainer_ 设置为容器的条目标识符，将  _cbEIDContainer_ 设置为条目标识符中的字节计数。 
  
如果要将新条目添加到传出邮件的收件人列表中，将  _lpEIDContainer_ 设置为 NULL，将  _cbEIDContainer_ 设置为 0。 
  
如果要允许客户端应用程序的用户选择要创建的条目类型，请在  _cbEIDNewEntryTpl_ 中传递 0，在  _lpEIDNewEntryTpl_ 中传递 NULL。 **NewEntry** 显示 MAPI 一对一表，这是 MAPI 和会话支持的每个通讯簿提供程序的模板列表。 每个模板都可以为一个或多个地址类型创建收件人条目。 
  
如果要保留新条目的条目标识符，请传递  _lpcbEIDNewEntry_ 和  _lppEIDNewEntry_ 参数中的有效指针。 你负责在通过调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数完成此条目标识符后释放它。 
  
若要使用特定模板向可修改容器添加新条目，请使用以下过程：
  
1. 调用 [IMAPISupport：：OpenEntry](imapisupport-openentry.md) 方法打开目标容器，将  _lpEntryID_ 参数设置为容器的条目标识符。 
    
2. 调用目标容器 [的 IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法，将  _ulPropTag_ 参数设置为 **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) ，将  _lpiid_ 参数设置为 IID_IMAPITable。 容器将返回一个一对表，其中列出了它支持创建新条目的所有模板。 
    
3. 检索表示要创建的特定条目类型的模板的行。 **"PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) 列指示模板支持的地址类型。 
    
4. 调用 **IMAPISupport：：NewEntry，** 将  _lpEIDNewEntryTpl_ 参数设置为所选模板的条目标识符。 条目标识符是PR_ENTRYID (一) 中模板行的[PidTagEntryId](pidtagentryid-canonical-property.md)列的标识符。 在  _cbEIDContainer 中传递 0，在_  _lpEIDContainer_ 中传递 NULL。 如果要保留新条目的条目标识符，请传递  _lppEIDNewEntry_ 参数中的有效指针。 
    
## <a name="see-also"></a>另请参阅



[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPISupport::OpenEntry](imapisupport-openentry.md)
  
[PidTagCreateTemplates 规范属性](pidtagcreatetemplates-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

