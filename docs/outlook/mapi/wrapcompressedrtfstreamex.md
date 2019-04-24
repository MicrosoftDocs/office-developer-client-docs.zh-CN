---
title: WrapCompressedRTFStreamEx
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 45abee1c-d7fb-b0f9-522d-8ba34caf1094
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: af176c0ce327e6498a5d07f6d902c50f7323f813
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325772"
---
# <a name="wrapcompressedrtfstreamex"></a>WrapCompressedRTFStreamEx

**适用于**：Outlook 2013 | Outlook 2016 
  
解压缩采用压缩格式文本格式 (rtf) 的电子邮件的正文, 指示解压缩后的流的格式, 可以选择将解压缩的流转换为其本机格式, 并返回解压缩的流或转换后的本机流。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者:  <br/> |msmapi32  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Outlook  <br/> |
   
```cpp
HRESULT __stdcall WrapCompressedRTFStreamEx( 
    LPSTREAM            lpCompressedRTFStream, 
    CONST RTF_WCSINFO   *pWCSInfo, 
    LPSTREAM            *lppUncompressedRTFStream, 
    RTF_WCSRETINFO      *pRetInfo); 

```

## <a name="parameters"></a>参数

_lpCompressedRTFStream_
  
> 实时这是一个指向在邮件的[PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md)中打开的流的指针。 
    
_pWCSInfo_
  
> 实时这是指向 
    
   包含函数的选项的[RTF_WCSINFO](rtf_wcsinfo.md)结构。 
    
_lppUncompressedRTFStream_
  
> 排除这是指向解压缩的 RTF 流的返回位置的指针。 
    
_pRetInfo_
  
> 排除这是指向[RTF_WCSRETINFO](rtf_wcsretinfo.md)结构的指针, 该结构包含有关返回的解压缩流格式的信息。 
    
## <a name="return-values"></a>返回值

S_OK 
  
- 函数调用成功。
    
MAPI_E_INVALID_PARAMETER 
  
- 如果**MAPI_NATIVE_BODY**标志与*pWCSInfo*所指向的**RTF_WCSINFO**结构的**ulFlags**字段中的**MAPI_MODIFY**标志组合在一起, 则会返回此内容。 
    
## <a name="remarks"></a>注解

**WrapCompressedRTFStreamEx**使您可以通过解压缩流来访问封装在压缩 RTF 中的电子邮件的正文, 返回解压缩后的流及其格式, 以及 (可选) 本机正文流。 本机正文流可以是 RTF、纯文本或 HTML 格式。 
  
Microsoft Office Outlook 对象模型提供**MailItem**对象的**Body**属性和[MailItem 属性 (Outlook)](https://msdn.microsoft.com/library/f635a0bc-20b7-206c-f558-a4ca2519670f%28Office.15%29.aspx) , 该属性指示正文文本的格式。 根据设计, outlook 不信任的解决方案会调用由 outlook 安全防护程序生成的安全对话框。 使用导出的 MAPI 函数**WrapCompressedRTFStreamEx**允许解决方案使用 MAPI 而不是 Outlook 对象模型, 并避免出现这些安全对话框。 
  
由于**\_mapi NATIVE_BODY**标记不能与*pWCSInfo*所指向的**RTF\_WCSINFO**结构的**ulFlags**字段中的**mapi\_MODIFY**标志组合在一起, 因此只能访问本机在只读模式下的正文流。 若要以读/写模式访问本机正文流, 应使用**WrapCompressedRTFStream**函数。 
  
## <a name="see-also"></a>另请参阅

- [检索压缩 RTF 格式的邮件正文, 并将其转换为本机格式](how-to-retrieve-the-body-of-a-message-in-compressed-rtf-and-convert.md)

