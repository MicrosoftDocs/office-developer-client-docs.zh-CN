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
ms.openlocfilehash: fefd81a7d6cdfda24df93ec928cd3305cb8ef8be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775244"
---
# <a name="iaddrbookcreateoneoff"></a>IAddrBook::CreateOneOff

  
  
**适用于**： Outlook 
  
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
  
> [in]一个指向收件人的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值。 _LpszName_参数可以是 NULL。 
    
 _lpszAdrType_
  
> [in]一个指向的收件人，例如传真或 SMTP 地址类型。 _LpszAdrType_参数不能为 NULL。 
    
 _lpszAddress_
  
> [in]一个指向收件人的地址。 _LpszAddress_参数不能为 NULL。 
    
 _ulFlags_
  
> [in]位掩码的标志影响一次性收件人。 可以设置以下标志：
    
MAPI_SEND_NO_RICH_INFO 
  
> 收件人无法处理格式化的消息内容。 如果设置 MAPI_SEND_NO_RICH_INFO，MAPI 将收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。 如果未设置 MAPI_SEND_NO_RICH_INFO，MAPI 设为 true，此属性，除非由_lpszAddress_指向的收件人的消息地址被解释为 Internet 地址。 在这种情况下，MAPI 将**PR_SEND_RICH_INFO**设置为 FALSE。 
    
MAPI_UNICODE 
  
> 显示名称、 地址类型和地址采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，这些字符串是以 ANSI 格式。
    
 _lpcbEntryID_
  
> [输出]一个指向_lppEntryID_参数指向该条目标识符中的字节数。 
    
 _lppEntryID_
  
> [输出]指向一次性收件人的项标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 一次性条目标识符已成功创建。
    
## <a name="remarks"></a>说明

客户端调用**CreateOneOff**方法创建的项标识符一次性收件人 — 不属于任何容器与任何当前加载的地址簿提供程序的收件人。 一次性收件人可以会话有任何一种由一个活动地址簿提供程序支持的地址。 
  
一次性收件人通常是使用其特定地址类型的模板创建的。 支持的地址类型通讯簿提供程序提供的模板。 客户端应用程序的用户输入到模板相关信息。
  
MAPI 的显示名称、 地址类型和**CreateOneOff**地址参数支持 Unicode 字符的字符串。
  
MAPI_SEND_NO_RICH_INFO 标志控制是否以及每封邮件发送带格式的文本中富文本格式 (RTF)。 传输中性封装格式 (TNEF) — 用于传输格式格式化文本 — 发送的大多数传输提供程序，无论收件人将其**PR_SEND_RICH_INFO**属性的设置。 这不是使用人际邮件的客户端消息的问题。 但是，因为 TNEF 通常用于发送自定义邮件类的自定义属性，则不支持可以是基于窗体的客户端或客户端需要自定义的 MAPI 属性的问题。 有关详细信息，请参阅[TNEF 发送邮件](sending-messages-with-tnef.md)。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|Mapiabfunctions.cpp  <br/> |AddOneOffAddress  <br/> |MFCMAPI 使用**CreateOneOff**方法创建的任何通讯簿中找不到的地址条目 ID。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

