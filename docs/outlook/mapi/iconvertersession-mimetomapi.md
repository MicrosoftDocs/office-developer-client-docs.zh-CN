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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326927"
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
  
> 实时MIME 流的[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口。 
    
 _pmsg_
  
> 排除指向要加载的邮件的指针。 有关**LPMESSAGE**的类型定义, 请参阅 mapidefs.h。
    
 _pszSrcSrv_
  
> 实时此值必须为**null**。
    
 _ulFlags_
  
> 实时此参数标识在转换过程中要采取的任何特殊操作。 如果不执行任何特定操作, 则必须为零 (0), 或以下值的组合:
    
CCSF_EMBEDDED_MESSAGE
  
> 发送/发送的信息将保留在 X-未发送中。
    
CCSF_SMTP
  
> MIME 流适用于简单 MAPI 传输协议 (SMTP) 邮件。
    
CCSF_INCLUDE_BCC
  
> MIME 流的密件抄送收件人应包含在 MAPI 邮件中。
    
CCSF_USE_RTF
  
> MIME 流的 HTML 正文应转换为 MAPI 邮件中的格式文本格式 (rtf)。

CCSF_GLOBAL_MESSAGE
> 转换器应将 MIME 流处理为国际邮件 (EAI/RFC6530)。 在 Outlook 2013 中不受支持。
    
## <a name="return-value"></a>返回值

E_INVALIDARG
  
> 指示_pstm_为**null**、 _pmsg_为**null**或_ulFlags_无效。 
    
## <a name="remarks"></a>注解

如果已将**CCSF_USE_RTF**指定为_ulFlags_的一部分, 且目标邮件存储库同时支持 html 和 rtf 格式, 则 MAPI 邮件将转换为 html 或 rtf 格式。 如果邮件转换为 rtf 格式, 则转换后的格式将被压缩为 rtf 格式, 任何 HTML 将嵌入在压缩的 RTF 字符串中, 并且该字符串将包含在[PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md)中。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MapiMime  <br/> |ImportEMLToIMessage  <br/> |MFCMAPI 使用 MimeToMAPI 将 .eml 文件转换为 MAPI 邮件。  <br/> |
|MapiMime  <br/> |ExportIMessageToEML  <br/> |MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 .eml 文件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IConverterSession : IUnknown](iconvertersessioniunknown.md)
  
[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)
  
[IConverterSession::SetAdrBook](iconvertersession-setadrbook.md)
  
[IConverterSession::SetCharSet](iconvertersession-setcharset.md)
  
[IConverterSession::SetEncoding](iconvertersession-setencoding.md)
  
[IConverterSession::SetSaveFormat](iconvertersession-setsaveformat.md)
  
[IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)


[MAPI 常量](mapi-constants.md)

