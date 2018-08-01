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
ms.openlocfilehash: e6880a32e30b8f208ce5ba0a2d30e635ff464461
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775279"
---
# <a name="iconvertersessionsetadrbook"></a>IConverterSession::SetAdrBook

  
  
**适用于**： Outlook 
  
指定到 MIME 转换器 MAPI 解析不明确的地址，将 MAPI 邮件转换为 MIME 流时使用可选 MAPI 通讯簿。
  
```cpp
HRESULT IConverterSession::SetAdrBook( 
LPADRBOOK pab); 
```

## <a name="parameters"></a>参数

 _pab_
  
> [in]指向[IAddrBook: IMAPIProp](iaddrbookimapiprop.md)接口用于与 MIME 转换 MAPI。 将此参数设置为**null** ，当不再需要通讯簿中;这释放接口并将转换器重置为不使用任何通讯簿。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 成功函数调用。
    
## <a name="remarks"></a>说明

转换 MAPI 邮件 MIME 流通常不需要登录到 MAPI 配置文件。 但是，指定转换的 MAPI 通讯簿需要登录到一个配置文件来获取通讯簿。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MapiMime.cpp  <br/> |ImportEMLToIMessage  <br/> |MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。  <br/> |
|MapiMime.cpp  <br/> |ExportIMessageToEML  <br/> |MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IConverterSession : IUnknown](iconvertersessioniunknown.md)
  
[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)
  
[IConverterSession::MIMEToMAPI](iconvertersession-mimetomapi.md)
  
[IConverterSession::SetCharSet](iconvertersession-setcharset.md)
  
[IConverterSession::SetEncoding](iconvertersession-setencoding.md)
  
[IConverterSession::SetSaveFormat](iconvertersession-setsaveformat.md)
  
[IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)

