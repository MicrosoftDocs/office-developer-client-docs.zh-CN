---
title: IConverterSessionSetSaveFormat
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.SetCharSet
api_type:
- COM
ms.assetid: e5308a94-5191-2109-a881-b4f4a7ff1c61
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f1a4834fc600cc93eeb7fc96563723326c7f2169
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775291"
---
# <a name="iconvertersessionsetsaveformat"></a>IConverterSession::SetSaveFormat

**适用于**： Outlook 
  
在其中转换器将返回 MIME 流[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)中的格式设置。
  
```cpp
HRESULT IConverterSession::SetSaveFormat ( 
     MIMESAVETYPE mstSaveFormat 
);
```

## <a name="parameters"></a>参数

_mstSaveFormat_
  
> [in]保存格式用于 MIME 流。 有关详细信息，请参阅枚举类型[MIMESAVETYPE](http://msdn.microsoft.com/en-us/library/ms715128%28VS.85%29.aspx)。
    
  - **SAVE_RFC1521**： 使用 MIME，这是默认值。      
  - **SAVE_RFC822**： 使用 uuencode。
    
## <a name="return-values"></a>返回值

S_OK
  
> 呼叫成功。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MapiMime.cpp  <br/> |ImportEMLToIMessage  <br/> |MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。  <br/> |
|MapiMime.cpp  <br/> |ExportIMessageToEML  <br/> |MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [IConverterSession : IUnknown](iconvertersessioniunknown.md)
- [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)
- [IConverterSession::MIMEToMAPI](iconvertersession-mimetomapi.md)
- [IConverterSession::SetAdrBook](iconvertersession-setadrbook.md)
- [IConverterSession::SetCharSet](iconvertersession-setcharset.md)
- [IConverterSession::SetEncoding](iconvertersession-setencoding.md)
- [IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)
- [MAPI 常量](mapi-constants.md)

