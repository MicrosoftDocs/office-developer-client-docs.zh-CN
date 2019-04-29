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
  
从**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中使用的压缩格式创建未压缩的 rtf 格式文本流。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
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
  
> 实时指向在邮件的 PR_RTF_COMPRESSED 属性上打开的流的指针。 
    
 _ulFlags_
  
> 实时函数的选项标志的位掩码。 可以设置以下标志:
    
MAPI_MODIFY 
  
> 客户端是否打算读取或写入返回的已包装流接口。 
    
STORE_UNCOMPRESSED_RTF 
  
> 应将未压缩的 RTF 写入_lpCompressedRTFStream_指向的流。
    
 _lpUncompressedRTFStream_
  
> 排除指向**WrapCompressedRTFStream**的位置的指针, 该位置返回未压缩的 RTF 的流。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

如果在_ulFlags_参数中传递了 MAPI_MODIFY 标志, 则必须已打开_lpCompressedRTFStream_参数以进行读取和写入。 新的、未压缩的 RTF 文本应写入_lpUncompressedRTFStream_中返回的 stream 接口。 由于无法追加现有流, 因此必须写入整个消息文本。 
  
如果在_ulFlags_参数中传递零, 则_lpCompressedRTFStream_可能会以只读的打开。 仅可从_lpUncompressedRTFStream_中返回的流接口读取整个邮件文本。 无法在流的中间开始搜索。 
  
 **WrapCompressedRTFStream**假定压缩流的指针设置为流的开头。 返回的未压缩流不支持某些 OLE **IStream**方法。 其中包括**IStream:: Clone**、 **istream:: LockRegion**、 **istream:: Revert**、 **IStream:: Seek**、 **IStream:: SetSize**、 **istream:: Stat**和**IStream:: UnlockRegion**。 若要复制到整个流, 需要具有读/写循环。 
  
由于客户端以未压缩格式写入新 RTF, 因此它应使用**WrapCompressedRTFStream**, 而不是直接写入流。 RTF 感知客户端应在**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中搜索 STORE_UNCOMPRESSED_RTF 标志, 并将其传递到**WrapCompressed RTFStream** (如果已设置)。 
  
## <a name="see-also"></a>另请参阅



[RTFSync](rtfsync.md)

