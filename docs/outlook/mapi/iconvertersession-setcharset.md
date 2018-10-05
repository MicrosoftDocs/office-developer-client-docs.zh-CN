---
title: IConverterSessionSetCharSet
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
ms.assetid: 25af3683-3a65-2d39-6f6e-76c8d36f866d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 14b2904e57852c564395f4b27c9d5270afd1454a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385723"
---
# <a name="iconvertersessionsetcharset"></a>IConverterSession::SetCharSet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定一个可选的字符的 MAPI 时设置为 MIME 转换器使用将 MAPI 邮件转换为 MIME 流。
  
```cpp
HRESULT SetCharset( 
     BOOL fApply, 
     HCHARSET hcharset, 
     CSETAPPLYTYPE csetapplytype); 
```

## <a name="parameters"></a>参数

 _fApply_
  
> [in]指示是否使用转换为特定字符集。 此参数设置为**true**可应用后续转换中的字符集。 如果您不再希望应用任何特定的字符集，并返回到后续的消息的默认值，请将此参数设置为**false** 。 
    
 _hcharset_
  
> [in]设置 Windows Mail 的 mimeole.h 中定义的字符句柄。 指定**null**以指定您不希望应用任何特定的字符集。 对于非**null**值，使用如[MimeOleGetCodePageCharset](https://msdn.microsoft.com/library/ms714746%28VS.85%29.aspx)函数获取句柄的字符集。 
    
 _csetapplytype_
  
> [in]指示如何应用转换一条消息，根据定义设置 Windows Mail 的 mimeole.h 中的字符。
    
## <a name="return-value"></a>返回值

S_OK
  
> 成功函数调用。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MapiMime.cpp  <br/> |ImportEMLToIMessage  <br/> |MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。  <br/> |
|MapiMime.cpp  <br/> |ExportIMessageToEML  <br/> |MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IConverterSession : IUnknown](iconvertersessioniunknown.md)
  
[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)
  
[IConverterSession::MIMEToMAPI](iconvertersession-mimetomapi.md)
  
[IConverterSession::SetAdrBook](iconvertersession-setadrbook.md)
  
[IConverterSession::SetEncoding](iconvertersession-setencoding.md)
  
[IConverterSession::SetSaveFormat](iconvertersession-setsaveformat.md)
  
[IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)

