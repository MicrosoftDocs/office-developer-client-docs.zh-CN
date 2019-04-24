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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322398"
---
# <a name="imapisupportcreateoneoff"></a>IMAPISupport::CreateOneOff

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为一次性地址创建条目标识符。
  
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
  
> 实时指向收件人的显示名称的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的指针。 _lpszName_参数可以为 NULL。 
    
 _lpszAdrType_
  
> 实时指向收件人的地址类型 (如传真、SMTP 或 X500) 的指针。 _lpszAdrType_参数不能为 NULL。 
    
 _lpszAddress_
  
> 实时指向收件人的邮件地址的指针。 _lpszAddress_参数不能为 NULL。 
    
 _ulFlags_
  
> 实时影响一次性收件人的标志的位掩码。 可以设置以下标志:
    
MAPI_SEND_NO_RICH_INFO 
  
> 收件人无法处理格式化的邮件内容。 如果设置了 MAPI_SEND_NO_RICH_INFO, MAPI 会将收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。 如果未设置 MAPI_SEND_NO_RICH_INFO, 则 MAPI 会将此属性设置为 TRUE, 除非收件人指向的收件人的__ 邮件地址被解释为 Internet 地址。 在这种情况下, MAPI 会将**PR_SEND_RICH_INFO**设置为 FALSE。 
    
MAPI_UNICODE 
  
> 显示名称、地址类型和地址采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则这些字符串将采用 ANSI 格式。
    
 _lpcbEntryID_
  
> 排除一个指针, 指向_lppEntryID_参数指向的条目标识符中的字节数。 
    
 _lppEntryID_
  
> 排除指向一次性收件人的条目标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建一次性条目标识符。
    
## <a name="remarks"></a>注解

**IMAPISupport:: CreateOneOff**方法是为所有服务提供程序支持对象实现的。 服务提供程序调用**CreateOneOff**为一次性收件人 (不属于任何当前已加载的通讯簿提供程序中的任何容器的收件人) 创建条目标识符。 
  
## <a name="notes-to-callers"></a>给调用方的说明

使用**CreateOneOff**返回的条目标识符完成后, 使用[MAPIFreeBuffer](mapifreebuffer.md)函数释放为条目标识符分配的内存。 
  
## <a name="notes-to-transport-providers"></a>传输提供程序注意事项

支持传输中性封装格式 (TNEF), 并使用**PR_SEND_RICH_INFO**属性的值来确定是否在传输邮件时使用 TNEF。 如果不支持 TNEF 或在请求邮件时不以这种格式发送邮件, 则可能会对需要自定义 MAPI 属性的基于表单的客户端或客户端产生问题。 这是因为 TNEF 通常用于发送自定义邮件类的自定义属性。 
  
## <a name="see-also"></a>另请参阅



[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagDisplayName 规范属性](pidtagdisplayname-canonical-property.md)
  
[PidTagSendRichInfo 规范属性](pidtagsendrichinfo-canonical-property.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

