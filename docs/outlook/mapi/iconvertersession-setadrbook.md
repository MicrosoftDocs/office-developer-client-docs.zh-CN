---
title: IConverterSessionSetAdrBook
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.SetAdrBook
api_type:
- COM
ms.assetid: d276ab19-17f4-01c7-4b44-b578e631b5fe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7645208e6a0256957deb3a71ba3e04ad125a6b61
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326892"
---
# <a name="iconvertersessionsetadrbook"></a>IConverterSession::SetAdrBook

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定 mapi 到 mime 转换器在将 MAPI 邮件转换为 MIME 流时用于解析不明确地址的可选 MAPI 通讯簿。
  
```cpp
HRESULT IConverterSession::SetAdrBook( 
LPADRBOOK pab); 
```

## <a name="parameters"></a>参数

 _.pab_
  
> 实时指向要在 MAPI 到 MIME 转换中使用的[IAddrBook: IMAPIProp](iaddrbookimapiprop.md)接口的指针。 当不再需要通讯簿时, 将此参数设置为**null** ;这将释放接口, 并将转换器重置为不使用任何通讯簿。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 函数调用成功。
    
## <a name="remarks"></a>注解

将 MAPI 邮件转换为 MIME 流通常不需要登录 MAPI 配置文件。 但是, 指定要转换的 MAPI 通讯簿需要登录到配置文件才能获取通讯簿。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MapiMime  <br/> |ImportEMLToIMessage  <br/> |MFCMAPI 使用 MimeToMAPI 将 .eml 文件转换为 MAPI 邮件。  <br/> |
|MapiMime  <br/> |ExportIMessageToEML  <br/> |MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 .eml 文件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IConverterSession : IUnknown](iconvertersessioniunknown.md)
  
[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)
  
[IConverterSession::MIMEToMAPI](iconvertersession-mimetomapi.md)
  
[IConverterSession::SetCharSet](iconvertersession-setcharset.md)
  
[IConverterSession::SetEncoding](iconvertersession-setencoding.md)
  
[IConverterSession::SetSaveFormat](iconvertersession-setsaveformat.md)
  
[IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)

