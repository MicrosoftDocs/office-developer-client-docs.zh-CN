---
title: IMAPISupportCreateOneOff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CreateOneOff
api_type:
- COM
ms.assetid: ee57d6e0-9de0-4427-97ce-371c1c01f3de
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1526ed54fd3773856b009c7c3570064f5a66df28
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594941"
---
# <a name="imapisupportcreateoneoff"></a>IMAPISupport::CreateOneOff

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
创建一个一次性地址的项标识符。
  
```cpp
HRESULT CreateOneOff(
  LPSTR lpszName,
  LPSTR lpszAdrType,
  LPSTR lpszAddress,
  ULONG ulFlags,
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a>参数

 _lpszName_
  
> [in]一个指向收件人**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的显示名称。 _LpszName_参数可以是 NULL。 
    
 _lpszAdrType_
  
> [in]一个指向 （如传真、 SMTP 或 X500） 的收件人的地址类型。 _LpszAdrType_参数不能为 NULL。 
    
 _lpszAddress_
  
> [in]一个指向收件人的邮件地址。 _LpszAddress_参数不能为 NULL。 
    
 _ulFlags_
  
> [in]位掩码的标志影响一次性收件人。 可以设置以下标志：
    
MAPI_SEND_NO_RICH_INFO 
  
> 收件人无法处理格式化的消息内容。 如果设置 MAPI_SEND_NO_RICH_INFO，MAPI 将收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。 如果未设置 MAPI_SEND_NO_RICH_INFO，MAPI 设为 true，此属性，除非由_lpszAddress_指向的收件人的消息地址被解释为 Internet 地址。 在这种情况下，MAPI 将**PR_SEND_RICH_INFO**设置为 FALSE。 
    
MAPI_UNICODE 
  
> 显示名称、 地址类型和地址采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，这些字符串是以 ANSI 格式。
    
 _lpcbEntryID_
  
> [输出]一个指向_lppEntryID_参数指向的项标识符的字节数的计数。 
    
 _lppEntryID_
  
> [输出]指向一次性收件人的项标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 一次性条目标识符已成功创建。
    
## <a name="remarks"></a>注解

**IMAPISupport::CreateOneOff**方法将执行所有服务提供商支持对象。 服务提供商调用**CreateOneOff**一次性收件人 （不属于任何容器与任何当前加载的地址簿提供程序的收件人） 创建的项标识符。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当您完成使用由**CreateOneOff**返回的项标识符时，释放内存分配给使用[MAPIFreeBuffer](mapifreebuffer.md)函数的项标识符。 
  
## <a name="notes-to-transport-providers"></a>Notes 传输提供程序

支持传输中性封装格式 (TNEF) 并使用**PR_SEND_RICH_INFO**属性的值来确定是否使用 TNEF 时传输一条消息。 不支持 TNEF 或不采用以下格式发送一条消息，要求时才可以是基于表单的客户端或客户端需要自定义的 MAPI 属性的问题。 这是因为 TNEF 通常用于发送自定义邮件类的自定义属性。 
  
## <a name="see-also"></a>另请参阅



[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagDisplayName 规范属性](pidtagdisplayname-canonical-property.md)
  
[PidTagSendRichInfo 规范属性](pidtagsendrichinfo-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

