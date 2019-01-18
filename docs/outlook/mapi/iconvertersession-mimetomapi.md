---
title: IConverterSessionMIMEToMAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.MIMEToMAPI
api_type:
- COM
ms.assetid: ee190ba7-9e71-97e4-7bf1-7b97adc73eed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 356f4470be26ae3803a53af1cec34b3ac6eb0cc9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723031"
---
# <a name="iconvertersessionmimetomapi"></a>IConverterSession::MIMEToMAPI

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 MIME 流转换为 MAPI 邮件。
  
```cpp
HRESULT IConverterSession:: MIMEToMAPI ( 
     LPSTREAM pstm, 
     LPMESSAGE pmsg, 
     LPCSTR pszSrcSrv, 
     ULONG ulFlags 
);
```

## <a name="parameters"></a>Parameters

 _pstm_
  
> [in]MIME 流[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口。 
    
 _pmsg_
  
> [输出]指向要加载的消息。 请参阅 mapidefs.h **LPMESSAGE**的类型定义。
    
 _pszSrcSrv_
  
> [in]此值必须为**空**。
    
 _ulFlags_
  
> [in]此参数用于标识转换期间执行任何特殊操作。 零 (0) 任何特定操作时要采取或以下值的组合，则必须将它：
    
CCSF_EMBEDDED_MESSAGE
  
> 发送/未发送信息保留在未发送的 X。
    
CCSF_SMTP
  
> 简单 MAPI 传输协议 (SMTP) 邮件 MIME 流。
    
CCSF_INCLUDE_BCC
  
> 应 MAPI 邮件中包含 MIME stream 的密件抄送收件人。
    
CCSF_USE_RTF
  
> MIME 流的 HTML 正文应转换到富文本格式 (RTF) 中的 MAPI 邮件。

CCSF_GLOBAL_MESSAGE
> 转换器应处理的 MIME 流作为国际邮件 (EAI/RFC6530)。 不支持 Outlook 2013。
    
## <a name="return-value"></a>返回值

E_INVALIDARG
  
> 指示_pstm_为**null**， _pmsg_为**null**，或者_ulFlags_无效。 
    
## <a name="remarks"></a>说明

如果您指定**CCSF_USE_RTF** _ulFlags_的一部分，目标消息存储库支持 HTML 和 RTF 的 MAPI 邮件将被转换为 HTML 或 RTF。 如果邮件转换为 RTF 时，将压缩转换的格式 RTF，将在压缩的 RTF 字符串中嵌入任何 HTML 和将[PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md)中包含字符串。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MapiMime.cpp  <br/> |ImportEMLToIMessage  <br/> |MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。  <br/> |
|MapiMime.cpp  <br/> |ExportIMessageToEML  <br/> |MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IConverterSession : IUnknown](iconvertersessioniunknown.md)
  
[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)
  
[IConverterSession::SetAdrBook](iconvertersession-setadrbook.md)
  
[IConverterSession::SetCharSet](iconvertersession-setcharset.md)
  
[IConverterSession::SetEncoding](iconvertersession-setencoding.md)
  
[IConverterSession::SetSaveFormat](iconvertersession-setsaveformat.md)
  
[IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)


[MAPI 常量](mapi-constants.md)

