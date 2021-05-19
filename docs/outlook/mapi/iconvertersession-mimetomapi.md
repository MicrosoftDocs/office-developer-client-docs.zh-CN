---
title: IConverterSessionMIMEToMAPI
manager: soliver
ms.date: 09/06/2019
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.MIMEToMAPI
api_type:
- COM
ms.assetid: ee190ba7-9e71-97e4-7bf1-7b97adc73eed
description: 上次修改时间：2019 年 9 月 6 日
ms.openlocfilehash: c9fcffa8ad4dc982e869f4ccd449e1377fb1ea57
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160284"
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

## <a name="parameters"></a>参数

 _pstm_
  
> [in] [MIME](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 流的 IStream 接口。 
    
 _pmsg_
  
> [in]指向要加载的消息的指针。 调用方必须提供消息，以便 API 填写，因此对象必须进入 [in]。 有关 **LPMESSAGE** 的类型定义，请参阅 mapidefs.h。
    
 _pszSrcSrv_
  
> [in]此值必须为 **null**。
    
 _ulFlags_
  
> [in]此参数标识转换过程中要执行的任何特殊操作。 如果不执行特定 (，) 0 或以下值的组合，则它必须为零：
    
CCSF_EMBEDDED_MESSAGE
  
> 已发送/未发送的信息将保留于 X-Unsent 中。
    
CCSF_SMTP
  
> MIME 流用于简单邮件传输协议 (SMTP) 邮件。
    
CCSF_INCLUDE_BCC
  
> MIME 流的 BCC 收件人应包含在 MAPI 邮件中。
    
CCSF_USE_RTF
  
> MIME 流的 HTML 正文应在 MAPI 邮件中 (RTF 格式) RTF 格式。

CCSF_GLOBAL_MESSAGE
> 转换器应该将 MIME 流作为国际邮件流 (EAI/RFC6530) 。 2013 Outlook不支持。
    
## <a name="return-value"></a>返回值

E_INVALIDARG
  
> 指示 _pstm_ 为 _null、pmsg_ 为 **null** 或 _ulFlags_ 无效。  
    
## <a name="remarks"></a>备注

如果 **已指定** CCSF_USE_RTF  _ulFlags_ 的一部分，并且目标邮件存储同时支持 HTML 和 RTF，则 MAPI 邮件将转换为 HTML 或 RTF。 如果邮件转换为 RTF，转换后的格式将压缩 RTF，任何 HTML 都将嵌入压缩的 RTF 字符串中，并且该字符串将包含在 [PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md)中。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MapiMime.cpp  <br/> |ImportEMLToIMessage  <br/> |MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。  <br/> |
|MapiMime.cpp  <br/> |ExportIMessageToEML  <br/> |MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 EML 文件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IConverterSession : IUnknown](iconvertersessioniunknown.md)
  
[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)
  
[IConverterSession::SetAdrBook](iconvertersession-setadrbook.md)
  
[IConverterSession::SetCharSet](iconvertersession-setcharset.md)
  
[IConverterSession::SetEncoding](iconvertersession-setencoding.md)
  
[IConverterSession::SetSaveFormat](iconvertersession-setsaveformat.md)
  
[IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)


[MAPI 常量](mapi-constants.md)

