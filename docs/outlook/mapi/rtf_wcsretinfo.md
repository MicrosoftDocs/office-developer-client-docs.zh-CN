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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426168"
---
# <a name="rtf_wcsretinfo"></a>RTF_WCSRETINFO

**适用于**：Outlook 2013 | Outlook 2016 
  
此结构提供有关以本机格式返回的流的信息，该流从解压缩以 RTF 格式压缩的 RTF 格式封装的邮件正文 (返回) 。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    ULONG size;    
    ULONG ulStreamFlags; 
} RTF_WCSRETINFO;
```

## <a name="members"></a>成员

_size_
  
> 数据库结构 **的大小RTF_WCSRETINFO** 字节数。 
    
_ulStreamFlags_
  
> 此值指示本机正文的格式。 只有在传递到 [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的 RTF_WCSINFO 结构的 _ulFlags_ 参数中传递 [MAPI_NATIVE_BODY](rtf_wcsinfo.md)标志时，此值才有效。  这可以是下列值之一： 
    
|||
|:-----|:-----|
|MAPI_NATIVE_BODY_TYPE_RTF  <br/> |只有在  _ulFlags_ 包含 MAPI_NATIVE_BODY 标志且正文为 RTF **时** ，才使用此值。  <br/> |
|MAPI_NATIVE_BODY_TYPE_PLAIN_TEXT  <br/> |只有在  _ulFlags_ 包含 MAPI_NATIVE_BODY **标志且** 正文为纯文本格式时，才使用此值。  <br/> |
|MAPI_NATIVE_BODY_TYPE_HTML  <br/> |此值仅在  _ulFlags_ 包括 MAPI_NATIVE_BODY **标志且** 正文为超文本标记语言 (HTML) 使用。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)

