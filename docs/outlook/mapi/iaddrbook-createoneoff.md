---
title: IAddrBookCreateOneOff
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.CreateOneOff
api_type:
- COM
ms.assetid: bcacfbdf-edff-4810-a985-e6d2c9271901
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 980ac82c6f7fcb5771a6013b3fb033b0bdfd05e0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427379"
---
# <a name="iaddrbookcreateoneoff"></a>IAddrBook::CreateOneOff

  
  
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
  
> [in]指向[PidTagDisplayName](pidtagdisplayname-canonical-property.md)属性中收件人PR_DISPLAY_NAME () 值的指针。 _lpszName_ 参数可以是 NULL。 
    
 _lpszAdrType_
  
> [in]指向收件人的地址类型（如 FAX 或 SMTP）的指针。 _lpszAdrType_ 参数不能为 NULL。 
    
 _lpszAddress_
  
> [in]指向收件人地址的指针。 _lpszAddress_ 参数不能为 NULL。 
    
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

客户端调用 **CreateOneOff** 方法为一次收件人（不属于任何当前加载的通讯簿提供程序的任何容器的收件人）创建条目标识符。 一对一收件人可以拥有会话的一个活动通讯簿提供程序支持的任何一种地址。 
  
一次收件人通常使用特定地址类型的模板创建。 支持地址类型的通讯簿提供程序提供模板。 客户端应用程序的用户将相关信息输入到模板中。
  
MAPI 支持 CreateOneOff 的 显示名称、地址类型和地址参数的 **Unicode 字符字符串**。
  
此MAPI_SEND_NO_RICH_INFO标志控制 RTF 格式格式 (格式) 文本是否随每封邮件一起发送。 传输中性封装格式 (TNEF) （一种用于传输格式文本的格式）由大多数传输提供程序发送，而不管收件人如何设置其 **PR_SEND_RICH_INFO** 属性。 对于处理不和谐消息的邮件客户端，这不是问题。 但是，由于 TNEF 通常用于发送自定义邮件类的自定义属性，因此不支持它可能是基于表单的客户端或需要自定义 MAPI 属性的客户端的问题。 有关详细信息，请参阅使用 [TNEF 发送邮件](sending-messages-with-tnef.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|Mapiabfunctions.cpp  <br/> |AddOneOffAddress  <br/> |MFCMAPI 使用 **CreateOneOff** 方法为在任何通讯簿中找不到的地址创建条目 ID。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

