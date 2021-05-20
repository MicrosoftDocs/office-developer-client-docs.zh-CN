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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430530"
---
# <a name="rtf_wcsinfo"></a>RTF_WCSINFO

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
利用此结构，您可以指定信息以压缩 RTF 格式 (RTF 格式解压缩邮件正文) （可选）以本机格式返回正文流。
  
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
  
> 结构的大小 **RTF_WCSINFO** 字节数。 
    
 _ulFlags_
  
> 这是 [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) 函数的选项标志的位掩码。 支持的选项标志包括： 
    
|||
|:-----|:-----|
|MAPI_MODIFY  <br/> |这指示客户端是否打算编写返回的封装流接口。  <br/> |
|STORE_UNCOMPRESSED_RTF  <br/> |这指示解压缩的 RTF 是否应该写入到 [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的 _lpCompressedRTFStream_ 指针指向的流。  <br/> |
|MAPI_NATIVE_BODY  <br/> |这指示在返回流之前解压缩的流是否也转换为本机正文。 此标志不能与 MAPI_MODIFY **标志组合** 。  <br/> |
   
 _ulInCodePage_
  
> 这是邮件的代码页值。 通常，此值从邮件上的 [PidTagInternetCodepage](pidtaginternetcodepage-canonical-property.md) 规范属性获取。 只有在 _ulFlags_**中传递** MAPI_NATIVE_BODY 标志时，才使用此值。 否则，将忽略此值。
    
 _ulOutCodePage_
  
> 这是您返回的解压缩流的代码页值。 如果设置为非零值 [，WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) 函数会将流转换为指定的代码页。 如果设置为零值，MAPI 将决定使用哪个代码页。 只有在 _ulFlags_ 中传递 MAPI_NATIVE_BODY 标记且正文格式不是 RTF 时，才使用此值。 否则，将忽略此值。
    
## <a name="see-also"></a>另请参阅



[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)

