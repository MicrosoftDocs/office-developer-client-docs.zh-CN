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
description: 上次修改时间：2017 年 9 月 20 日
ms.openlocfilehash: 55c547c4dae1acc3e9874edc7778f53a5d34f957
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326942"
---
# <a name="iconvertersessionmapitomimestm"></a>IConverterSession::MAPIToMIMEStm
 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
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
  
> [in]指向要转换的消息的指针。 有关 **LPMESSAGE** 的类型定义，请参阅 mapidefs.h。
    
 _pstm_
  
> [out]用于输出流的 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 接口。 
    
 _ulFlags_
  
>  [in]指示转换器的特定操作的标志： 
    
CCSF_8BITHEADERS
  
> 转换器应允许使用 8 位标头。
    
CCSF_EMBEDDED_MESSAGE
  
> 已发送/未发送的信息将保留于 X-Unsent 中。
    
CCSF_GLOBAL_MESSAGE
  
> 转换器应在 EAI/RFC6530 (生成国际) 。
    
CCSF_INCLUDE_BCC
  
> MAPI 邮件的 BCC 收件人应包含在 MIME 流中。
    
CCSF_NO_MSGID
  
> 请勿在传出Message-Id字段。
    
CCSF_NOHEADERS
  
> 转换器应忽略外部邮件的标题。
    
CCSF_PLAIN_TEXT_ONLY
  
> 转换器应只发送纯文本。
    
CCSF_SMTP
  
> 正在向转换器传递 SMTP 邮件。 必须始终设置此标志。
    
CCSF_USE_RTF
  
> 转换器应在 MIME 邮件中从 HTML 转换为 RTF 格式。
    
CCSF_USE_TNEF
  
> 转换器应在 MIME 邮件 (传输中性封装) TNEF 格式。
    
## <a name="return-values"></a>返回值

E_INVALIDARG
  
> 传递了无效标志，  *或者 pmsg*  或  *pstm*  为 NULL。 
    
## <a name="remarks"></a>备注

仅支持标准Outlook邮件类型。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MapiMime.cpp  <br/> |ImportEMLToIMessage  <br/> |MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。  <br/> |
|MapiMime.cpp  <br/> |ExportIMessageToEML  <br/> |MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 EML 文件。  <br/> |
   
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

