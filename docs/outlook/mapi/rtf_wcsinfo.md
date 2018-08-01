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
ms.openlocfilehash: c328e79b7e474369f11f8a4002e00137659db3c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778675"
---
# <a name="rtfwcsinfo"></a>RTF_WCSINFO

  
  
**适用于**： Outlook 
  
此结构使您可以指定要解压缩压缩富文本格式 (RTF) 中的邮件正文以及 （可选） 以其本机格式返回正文的流信息。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    ULONG size; 
    ULONG ulFlags; 
    ULONG ulInCodePage; 
    ULONG ulOutCodePage; 
} RTF_WCSINFO;

```

## <a name="members"></a>Members

 _size_
  
> **RTF_WCSINFO**结构以字节为单位的大小。 
    
 _ulFlags_
  
> 这是[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数选项标志的位掩码。 受支持的选项标志是： 
    
|||
|:-----|:-----|
|MAPI_MODIFY  <br/> |这指示客户端是否打算编写返回打包的流界面。  <br/> |
|STORE_UNCOMPRESSED_RTF  <br/> |这指示是否应记下解压缩后的 RTF 写入[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的_lpCompressedRTFStream_指针所指向的流。  <br/> |
|MAPI_NATIVE_BODY  <br/> |这指示是否记下解压缩后的流也返回流之前转换为本机正文。 不能与**MAPI_MODIFY**标志组合此标志。  <br/> |
   
 _ulInCodePage_
  
> 这是邮件的代码页值。 通常情况下，从邮件上的[PidTagInternetCodepage 规范属性](pidtaginternetcodepage-canonical-property.md)获取此值。 _UlFlags_中传递**MAPI_NATIVE_BODY**标志时才使用此值。 否则，此值将被忽略。
    
 _ulOutCodePage_
  
> 这是数据流的返回记下解压缩后所需的代码页值。 如果设置为非零值， [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数会将流转换为指定的代码页。 如果设置为零值，MAPI 决定要使用的代码页。 仅当**MAPI_NATIVE_BODY**标志传入中_ulFlags_，并且的正文格式不为 RTF 时，则使用此值。 否则，此值将被忽略。
    
## <a name="see-also"></a>另请参阅



[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)

