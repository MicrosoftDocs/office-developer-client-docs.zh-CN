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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349313"
---
# <a name="iaddrbookcreateoneoff"></a>IAddrBook::CreateOneOff

  
  
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
  
> 实时指向收件人的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值的指针。 _lpszName_参数可以为 NULL。 
    
 _lpszAdrType_
  
> 实时指向收件人的地址类型的指针, 如 "传真" 或 "SMTP"。 _lpszAdrType_参数不能为 NULL。 
    
 _lpszAddress_
  
> 实时指向收件人地址的指针。 _lpszAddress_参数不能为 NULL。 
    
 _ulFlags_
  
> 实时影响一次性收件人的标志的位掩码。 可以设置以下标志:
    
MAPI_SEND_NO_RICH_INFO 
  
> 收件人无法处理格式化的邮件内容。 如果设置了 MAPI_SEND_NO_RICH_INFO, MAPI 会将收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。 如果未设置 MAPI_SEND_NO_RICH_INFO, 则 MAPI 会将此属性设置为 TRUE, 除非收件人指向的收件人的__ 邮件地址被解释为 Internet 地址。 在这种情况下, MAPI 会将**PR_SEND_RICH_INFO**设置为 FALSE。 
    
MAPI_UNICODE 
  
> 显示名称、地址类型和地址采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则这些字符串将采用 ANSI 格式。
    
 _lpcbEntryID_
  
> 排除指向条目标识符中由_lppEntryID_参数指向的字节计数的指针。 
    
 _lppEntryID_
  
> 排除指向一次性收件人的条目标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功创建一次性条目标识符。
    
## <a name="remarks"></a>注解

客户端调用**CreateOneOff**方法为一次性收件人创建条目标识符, 即不属于任何当前已加载的通讯簿提供程序中任何容器的收件人。 一次性收件人可以具有该会话的一个活动通讯簿提供程序支持的任何类型的地址。 
  
一次性收件人通常是使用其特定地址类型的模板创建的。 支持该地址类型的通讯簿提供程序提供该模板。 客户端应用程序的用户将相关信息输入到模板中。
  
MAPI 支持**CreateOneOff**的显示名称、地址类型和地址参数的 Unicode 字符字符串。
  
MAPI_SEND_NO_RICH_INFO 标志控制是否随每封邮件一起发送 rtf 格式的格式化文本。 传输中性封装格式 (TNEF) —一种用于传输格式化文本的格式, 它由大部分传输提供程序发送, 而不管收件人如何设置其**PR_SEND_RICH_INFO**属性。 对于处理人际邮件的邮件客户端而言, 这并不是问题。 但是, 由于 TNEF 通常用于发送自定义邮件类别的自定义属性, 因此, 不支持需要自定义 MAPI 属性的基于表单的客户端或客户端可能会遇到问题。 有关详细信息, 请参阅[使用 TNEF 发送邮件](sending-messages-with-tnef.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|Mapiabfunctions  <br/> |AddOneOffAddress  <br/> |MFCMAPI 使用**CreateOneOff**方法为在任何通讯簿中找不到的地址创建条目 ID。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

