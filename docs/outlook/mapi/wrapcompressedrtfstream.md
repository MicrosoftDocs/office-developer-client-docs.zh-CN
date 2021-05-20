---
title: WrapCompressedRTFStream
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.WrapCompressedRTFStream
api_type:
- COM
ms.assetid: 0949e066-aa28-4ede-ac88-b2dccd5098e8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 710e0e2fc334194e33c6d8ba1296e4c7b1938bc0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439798"
---
# <a name="wrapcompressedrtfstream"></a>WrapCompressedRTFStream

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中使用的压缩格式创建未压缩 RTF (RT) F 格式的文本流。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT WrapCompressedRTFStream(
  LPSTREAM lpCompressedRTFStream,
  ULONG ulflags,
  LPSTREAM FAR * lpUncompressedRTFStream
);
```

## <a name="parameters"></a>参数

 _lpCompressedRTFStream_
  
> [in]指向在邮件的 PR_RTF_COMPRESSED 属性上打开的流的指针。 
    
 _ulFlags_
  
> [in]函数的选项标志的位掩码。 可以设置以下标志：
    
MAPI_MODIFY 
  
> 客户端是打算读取还是写入返回的封装流接口。 
    
STORE_UNCOMPRESSED_RTF 
  
> 未压缩的 RTF 应写入  _lpCompressedRTFStream 指向的流_
    
 _lpUncompressedRTFStream_
  
> [out]指向 **WrapCompressedRTFStream** 返回未压缩 RTF 的流的位置的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

如果在  _ulFlags_ 参数中传递 MAPI_MODIFY 标志，则必须已打开  _lpCompressedRTFStream_ 参数进行读取和写入。 新的未压缩 RTF 文本应写入  _lpUncompressedRTFStream 中返回的流接口_。 由于无法追加现有流，因此必须写入整个消息文本。 
  
如果在  _ulFlags_ 参数中传递零，  _则 lpCompressedRTFStream_ 可以只读打开。 只能从  _lpUncompressedRTFStream_ 中返回的流接口中读取整个消息文本。 无法从流中间开始搜索。 
  
 **WrapCompressedRTFStream** 假定压缩流的指针设置为流的开头。 返回的未压缩流不支持某些 OLE **IStream** 方法。 其中包括 **IStream：：Clone**、IStream：：LockRegion、IStream：：Revert、IStream：：Seek、IStream：：SetSize、IStream：：Stat 和 **IStream：：UnlockRegion。**     为了复制到整个流，需要读/写循环。 
  
由于客户端以未压缩的格式写入新的 RTF，因此它应当使用 **WrapCompressedRTFStream，** 而不是直接写入流。 RTF 感知客户端应在 PR_STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中搜索 **STORE_UNCOMPRESSED_RTF** 标志，如果已设置，则将其传递给 **WrapCompressed RTFStream。** 
  
## <a name="see-also"></a>另请参阅



[RTFSync](rtfsync.md)

