---
title: RTF_WCSINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0c94501e-0ec7-e836-33a7-adcf5a61b375
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6bec29aa0e88e0224f9cd6049553f2df6379e23d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344644"
---
# <a name="rtfwcsinfo"></a>RTF_WCSINFO

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通过此结构, 您可以指定信息以压缩的 rtf 格式 (rtf) 解压缩邮件正文, 也可以选择以本机格式返回正文流。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    ULONG size; 
    ULONG ulFlags; 
    ULONG ulInCodePage; 
    ULONG ulOutCodePage; 
} RTF_WCSINFO;

```

## <a name="members"></a>成员

 _size_
  
> 以字节数表示的**RTF_WCSINFO**结构的大小。 
    
 _ulFlags_
  
> 这是[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的选项标志的位掩码。 受支持的选项标志为: 
    
|||
|:-----|:-----|
|MAPI_MODIFY  <br/> |这指示客户端是否打算写入已返回的包装流接口。  <br/> |
|STORE_UNCOMPRESSED_RTF  <br/> |这指示是否应将解压缩的 RTF 写入[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的_lpCompressedRTFStream_指针指向的流。  <br/> |
|MAPI_NATIVE_BODY  <br/> |这指示在返回流之前, 是否将解压缩的流也转换为本机正文。 此标志不能与**MAPI_MODIFY**标志一起使用。  <br/> |
   
 _ulInCodePage_
  
> 这是邮件的代码页值。 通常, 此值是从邮件的[PidTagInternetCodepage 规范属性](pidtaginternetcodepage-canonical-property.md)获取的。 仅当在_ulFlags_中传递**MAPI_NATIVE_BODY**标志时, 才使用此值。 否则, 此值将被忽略。
    
 _ulOutCodePage_
  
> 这是所需的已返回的解压缩流的代码页值。 如果将此值设置为非零值, 则[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数会将流转换为指定的代码页。 如果将此值设置为零值, MAPI 将决定要使用的代码页。 仅当在_ulFlags_中传递**MAPI_NATIVE_BODY**标志且正文格式不是 RTF 时, 才使用此值。 否则, 此值将被忽略。
    
## <a name="see-also"></a>另请参阅



[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)

