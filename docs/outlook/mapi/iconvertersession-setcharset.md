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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336657"
---
# <a name="iconvertersessionsetcharset"></a>IConverterSession::SetCharSet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定 mapi 到 mime 转换器在将 mapi 邮件转换为 mime 流时使用的一组可选字符集。
  
```cpp
HRESULT SetCharset( 
     BOOL fApply, 
     HCHARSET hcharset, 
     CSETAPPLYTYPE csetapplytype); 
```

## <a name="parameters"></a>参数

 _fApply_
  
> 实时指示是否对转换使用特定的字符集。 将此参数设置为**true**可在后续转换中应用字符集。 如果您不再希望应用任何特定的字符集, 并返回到后续邮件的默认设置, 请将此参数设置为**false** 。 
    
 _hcharset_
  
> 实时在 Windows Mail mimeole 中定义的字符集的句柄。 指定**null**以指定不希望应用任何特定的字符集。 对于非**null**值, 请使用函数 (如[MimeOleGetCodePageCharset](https://msdn.microsoft.com/library/ms714746%28VS.85%29.aspx) ) 获取字符集的句柄。 
    
 _csetapplytype_
  
> 实时指示如何应用字符集以转换邮件, 如 mimeole 中的 Windows Mail 中所定义。
    
## <a name="return-value"></a>返回值

S_OK
  
> 函数调用成功。
    
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
  
[IConverterSession::SetAdrBook](iconvertersession-setadrbook.md)
  
[IConverterSession::SetEncoding](iconvertersession-setencoding.md)
  
[IConverterSession::SetSaveFormat](iconvertersession-setsaveformat.md)
  
[IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)

