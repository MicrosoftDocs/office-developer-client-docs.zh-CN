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
  
解压缩 RTF (RTF) 格式的电子邮件正文，指示解压缩流的格式，（可选）将解压缩的流转换为本机格式，并返回解压缩的流或已转换的本机流。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者：  <br/> |msmapi32.dll  <br/> |
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
  
> [in]这是一个指针，指向在 [邮件的 PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md) 上打开的流。 
    
_pWCSInfo_
  
> [in]This is a pointer to a 
    
   [RTF_WCSINFO](rtf_wcsinfo.md) 包含函数选项的一个结构。 
    
_lppUncompressedRTFStream_
  
> [out]This is a pointer to the location where a stream for the decompressed RTF is returned. 
    
_pRetInfo_
  
> [out]This is a pointer to a [RTF_WCSRETINFO](rtf_wcsretinfo.md) structure that contains information about the format of the returned decompressed stream. 
    
## <a name="return-values"></a>返回值

S_OK 
  
- 函数调用成功。
    
MAPI_E_INVALID_PARAMETER 
  
- 如果 MAPI_NATIVE_BODY 标记 **与** *pWCSInfo* 指向的 RTF_WCSINFO 结构的 **ulFlags** 字段中的 **MAPI_MODIFY** 标志组合在一起 **，** 则返回此标记。 
    
## <a name="remarks"></a>备注

**WrapCompressedRTFStreamEx** 允许你通过解压缩流访问封装在压缩 RTF 中的电子邮件正文、返回解压缩的流及其格式以及本机正文流（可选）。 本机正文流可以是 RTF、纯文本或 HTML 格式。 
  
The Microsoft Office Outlook object model provides a **Body** property for **MailItem** objects and a [MailItem.BodyFormat Property (Outlook)](https://msdn.microsoft.com/library/f635a0bc-20b7-206c-f558-a4ca2519670f%28Office.15%29.aspx) that indicates the format of the body text. 根据设计，Outlook 不信任的解决方案会调用由 Outlook 安全防护生成的安全对话框。 使用导出的 MAPI 函数 **WrapCompressedRTFStreamEx** 允许解决方案使用 MAPI 而不是 Outlook 对象模型，并避免这些安全对话框。 
  
由于 **MAPI \_ NATIVE_BODY** 标志不能与 *pWCSInfo* 指向的 **RTF \_ WCSINFO** 结构的 **ulFlags** 字段中的 **MAPI \_ MODIFY** 标志组合在一起，因此只能在只读模式下访问本机正文流。 若要在读/写模式下访问本机正文流，你应该使用 **WrapCompressedRTFStream** 函数。 
  
## <a name="see-also"></a>另请参阅

- [检索压缩 RTF 格式的邮件正文并将其转换为本机格式](how-to-retrieve-the-body-of-a-message-in-compressed-rtf-and-convert.md)

