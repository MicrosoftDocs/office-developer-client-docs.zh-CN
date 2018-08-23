---
title: IConverterSessionMAPIToMIMEStm
ms.date: 9/20/2017
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.MAPIToMIMEStm
api_type:
- COM
ms.assetid: 8660c701-f7f4-8d92-7984-5dae7f677783
description: 上次修改时间： 2017 年 9 月 20，
ms.openlocfilehash: bcbc3d21a03c1585288ad23b1fb2d311d686f55c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570448"
---
# <a name="iconvertersessionmapitomimestm"></a>IConverterSession::MAPIToMIMEStm
 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
将 MAPI 邮件转换为 MIME 流。
  
```cpp
HRESULT IConverterSession::MAPIToMIMEStm( 
    LPMESSAGE pmsg, 
    LPSTREAM pstm, 
    ULONG ulFlags 
);
```

## <a name="parameters"></a>参数

 _pmsg_
  
> [in]指向要转换的消息的指针。 请参阅 mapidefs.h **LPMESSAGE**的类型定义。
    
 _pstm_
  
> [输出]要输出流[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口。 
    
 _ulFlags_
  
>  [in]这些标志指示转换器的特定操作： 
    
CCSF_8BITHEADERS
  
> 转换器应允许 8 位标头。
    
CCSF_EMBEDDED_MESSAGE
  
> 发送/未发送信息保留在未发送的 X。
    
CCSF_GLOBAL_MESSAGE
  
> 转换器应该构建国际邮件 (EAI/RFC6530)。
    
CCSF_INCLUDE_BCC
  
> 应 MIME 用于将 stream 中包含的 MAPI 邮件的密件抄送收件人。
    
CCSF_NO_MSGID
  
> 传出消息中不包括消息 Id 字段。
    
CCSF_NOHEADERS
  
> 转换器忽略外部邮件的标头。
    
CCSF_PLAIN_TEXT_ONLY
  
> 转换器应只发送纯文本。
    
CCSF_SMTP
  
> 转换器所传递的 SMTP 邮件。 必须始终设置此标志。
    
CCSF_USE_RTF
  
> 转换器应为 MIME 邮件中的 RTF 格式转换的 HTML。
    
CCSF_USE_TNEF
  
> 转换器应该 MIME 邮件中使用传输中性封装格式 (TNEF) 格式。
    
## <a name="return-values"></a>返回值

E_INVALIDARG
  
> 传递标志无效，或*pmsg*或*pstm*为 NULL。 
    
## <a name="remarks"></a>注解

仅支持标准的 Outlook 邮件类型。
  
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
  
[IConverterSession::SetAdrBook](iconvertersession-setadrbook.md)
  
[IConverterSession::SetCharSet](iconvertersession-setcharset.md)
  
[IConverterSession::SetEncoding](iconvertersession-setencoding.md)
  
[IConverterSession::SetSaveFormat](iconvertersession-setsaveformat.md)
  
[IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)
  
[PidTagMessageEditorFormat 规范属性](pidtagmessageeditorformat-canonical-property.md)
  
[PidLidUseTnef 规范属性](pidlidusetnef-canonical-property.md)


[MAPI 常量](mapi-constants.md)

