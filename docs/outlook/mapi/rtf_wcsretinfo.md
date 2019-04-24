---
title: RTF_WCSRETINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62561d8d-33cb-e482-7fa0-132afe2b464a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cfa18c215fc98610b836db31e2a07581291910be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315783"
---
# <a name="rtfwcsretinfo"></a>RTF_WCSRETINFO

**适用于**：Outlook 2013 | Outlook 2016 
  
此结构提供了从解压缩以压缩的 rtf 格式 (RTF) 封装的邮件正文返回的本机格式的信息。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    ULONG size;    
    ULONG ulStreamFlags; 
} RTF_WCSRETINFO;
```

## <a name="members"></a>成员

_size_
  
> 以字节数表示的**RTF_WCSRETINFO**结构的大小。 
    
_ulStreamFlags_
  
> 这是一个指示本机正文的格式的值。 仅当**MAPI_NATIVE_BODY**标志在传递给[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的[RTF_WCSINFO](rtf_wcsinfo.md)结构的_ulFlags_参数中传递时, 此值才有效。 此值可以是下列值之一: 
    
|||
|:-----|:-----|
|MAPI_NATIVE_BODY_TYPE_RTF  <br/> |仅当_ulFlags_包含**MAPI_NATIVE_BODY**标志, 且正文为 RTF 时才使用此值。  <br/> |
|MAPI_NATIVE_BODY_TYPE_PLAIN_TEXT  <br/> |仅当_ulFlags_包含**MAPI_NATIVE_BODY**标志, 且正文为纯文本格式时才使用此值。  <br/> |
|MAPI_NATIVE_BODY_TYPE_HTML  <br/> |仅当_ulFlags_包含**MAPI_NATIVE_BODY**标志, 并且正文是超文本标记语言 (HTML) 格式时, 才使用此值。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)

