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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9571d51e01c2d58d9b8a9a913ba2c210ae0bd44d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411993"
---
# <a name="imapisupportcreateoneoff"></a>IMAPISupport::CreateOneOff

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为一次地址创建条目标识符。
  
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
  
> [in]指向 [PidTagDisplayName 显示名称 PidTagDisplayName](pidtagdisplayname-canonical-property.md) **PR_DISPLAY_NAME (** 收件人) 指针。 _lpszName_ 参数可以是 NULL。 
    
 _lpszAdrType_
  
> [in]指向收件人的地址类型 (如 FAX、SMTP 或 X500) 的指针。 _lpszAdrType_ 参数不能为 NULL。 
    
 _lpszAddress_
  
> [in]指向收件人的邮件地址的指针。 _lpszAddress_ 参数不能为 NULL。 
    
 _ulFlags_
  
> [in]影响一次收件人的标志的位掩码。 可以设置以下标志：
    
MAPI_SEND_NO_RICH_INFO 
  
> 收件人无法处理格式化的邮件内容。 如果MAPI_SEND_NO_RICH_INFO，MAPI 将收件人的 PR_SEND_RICH_INFO ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 设置为 FALSE。  如果未MAPI_SEND_NO_RICH_INFO，MAPI 将此属性设置为 TRUE，除非  _lpszAddress_ 指向的收件人的邮件地址被解释为 Internet 地址。 在这种情况下，MAPI **将PR_SEND_RICH_INFO** FALSE。 
    
MAPI_UNICODE 
  
> 该显示名称、地址类型和地址采用 Unicode 格式。 如果未MAPI_UNICODE，则这些字符串采用 ANSI 格式。
    
 _lpcbEntryID_
  
> [out]指向  _lppEntryID_ 参数指向的条目标识符中的字节计数的指针。 
    
 _lppEntryID_
  
> [out]指向指向一次收件人的条目标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建一次项标识符。
    
## <a name="remarks"></a>备注

**IMAPISupport：：CreateOneOff** 方法针对所有服务提供商支持对象实现。 服务提供商调用 **CreateOneOff** 为一次收件人创建条目标识符 (该收件人不属于当前加载的任何通讯簿提供程序中的容器) 。 
  
## <a name="notes-to-callers"></a>给调用方的说明

使用完 **CreateOneOff** 返回的条目标识符后，使用 [MAPIFreeBuffer](mapifreebuffer.md) 函数释放为条目标识符分配的内存。 
  
## <a name="notes-to-transport-providers"></a>对传输提供程序的注释

支持传输中性封装 (TNEF) 并使用 **PR_SEND_RICH_INFO** 属性的值来确定在传输邮件时是否使用 TNEF。 不支持 TNEF 或在请求时不以此格式发送邮件可能是基于表单的客户端或需要自定义 MAPI 属性的客户端的问题。 这是因为 TNEF 通常用于发送自定义邮件类的自定义属性。 
  
## <a name="see-also"></a>另请参阅



[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagDisplayName 规范属性](pidtagdisplayname-canonical-property.md)
  
[PidTagSendRichInfo 规范属性](pidtagsendrichinfo-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

