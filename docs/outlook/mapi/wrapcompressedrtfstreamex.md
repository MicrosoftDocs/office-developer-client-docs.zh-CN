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
ms.openlocfilehash: 4b7e59c9ffccb2e063962b2cc4947b4fa54757bf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572716"
---
# <a name="wrapcompressedrtfstreamex"></a>WrapCompressedRTFStreamEx

**适用于**： Outlook 2013 |Outlook 2016 
  
解压缩是在压缩富文本格式 (RTF) 中，电子邮件的正文将指示记下解压缩后的 stream 的格式，（可选） 将记下解压缩后的流转换为其本机格式，并返回记下解压缩后的流或转换后的本机流。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出：  <br/> |msmapi32.dll  <br/> |
|调用：  <br/> |客户端  <br/> |
|通过实现：  <br/> |Outlook  <br/> |
   
```cpp
HRESULT __stdcall WrapCompressedRTFStreamEx( 
    LPSTREAM            lpCompressedRTFStream, 
    CONST RTF_WCSINFO   *pWCSInfo, 
    LPSTREAM            *lppUncompressedRTFStream, 
    RTF_WCSRETINFO      *pRetInfo); 

```

## <a name="parameters"></a>参数

_lpCompressedRTFStream_
  
> [in]这是指向打开一条消息[PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md)流的指针。 
    
_pWCSInfo_
  
> [in]这是一个指向 
    
   [RTF_WCSINFO](rtf_wcsinfo.md)结构，其中包含函数的选项。 
    
_lppUncompressedRTFStream_
  
> [输出]这是指向记下解压缩后的 RTF 流返回其中的位置的指针。 
    
_pRetInfo_
  
> [输出]这是数据流的一个指向[RTF_WCSRETINFO](rtf_wcsretinfo.md)结构，其中包含返回记下解压缩后的格式信息。 
    
## <a name="return-values"></a>返回值

S_OK 
  
- 成功函数调用。
    
MAPI_E_INVALID_PARAMETER 
  
- 如果**MAPI_NATIVE_BODY**标志结合在由*pWCSInfo*指向**RTF_WCSINFO**结构的**ulFlags**字段中的**MAPI_MODIFY**标志，则返回此。 
    
## <a name="remarks"></a>注解

记下解压缩后的流和其格式，和 （可选） 的本机正文流，使您可以访问由解压缩流封装在压缩 RTF 电子邮件的正文返回**WrapCompressedRTFStreamEx** 。 本机正文流可以的 RTF、 纯文本或 HTML。 
  
Microsoft Office Outlook 对象模型提供的**MailItem**对象和[MailItem.BodyFormat 属性 (Outlook)](http://msdn.microsoft.com/library/f635a0bc-20b7-206c-f558-a4ca2519670f%28Office.15%29.aspx)指示正文文本的格式的**Body**属性。 按照设计，不受信任的 Outlook 解决方案调用生成的 Outlook 安全 Guard 的安全对话框。 使用导出 MAPI 函数**WrapCompressedRTFStreamEx**允许使用 MAPI，而不是 Outlook 对象模型，并避免这些安全对话框的解决方案。 
  
因为**MAPI\_NATIVE_BODY**标志不能组合与**MAPI\_修改** **ulFlags**字段中的标志**RTF\_WCSINFO**结构指向*pWCSInfo*，您只能访问本机在只读模式下的正文流。 若要访问本机正文流读/写模式，您应使用**WrapCompressedRTFStream**函数。 
  
## <a name="see-also"></a>另请参阅

- [检索压缩 RTF 格式的邮件正文，并将其转换为本机格式](how-to-retrieve-the-body-of-a-message-in-compressed-rtf-and-convert.md)

