---
title: RTF_WCSRETINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62561d8d-33cb-e482-7fa0-132afe2b464a
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 3a38a4604230c0aa3f5b0d104ae3b838f544b31d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778657"
---
# <a name="rtfwcsretinfo"></a>RTF_WCSRETINFO

**适用于**： Outlook 
  
此结构提供有关本机格式返回从解压缩封装压缩富文本格式 (RTF) 中的邮件正文中的流信息。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    ULONG size;    
    ULONG ulStreamFlags; 
} RTF_WCSRETINFO;
```

## <a name="members"></a>成员

_size_
  
> **RTF_WCSRETINFO**结构以字节为单位的大小。 
    
_ulStreamFlags_
  
> 这是一个值，指示本机正文的格式。 此值才有效如果传递给[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的[RTF_WCSINFO](rtf_wcsinfo.md)结构的_ulFlags_参数中传递**MAPI_NATIVE_BODY**标志。 这可以是下列值之一： 
    
|||
|:-----|:-----|
|MAPI_NATIVE_BODY_TYPE_RTF  <br/> |如果_ulFlags_包括**MAPI_NATIVE_BODY**标志，而且正文时 RTF，则仅使用此值。  <br/> |
|MAPI_NATIVE_BODY_TYPE_PLAIN_TEXT  <br/> |如果_ulFlags_包括**MAPI_NATIVE_BODY**标志，和正文采用纯文本格式，则仅使用此值。  <br/> |
|MAPI_NATIVE_BODY_TYPE_HTML  <br/> |如果_ulFlags_包括**MAPI_NATIVE_BODY**标志，而且正文时的超文本标记语言 (HTML) 格式，则仅使用此值。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)

