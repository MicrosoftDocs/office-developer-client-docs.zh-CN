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
ms.openlocfilehash: 9025bcebdd5e656070b31cd82e6519166a3e3791
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779119"
---
# <a name="wrapcompressedrtfstream"></a>WrapCompressedRTFStream

  
  
**适用于**： Outlook 
  
创建一个文本流中未压缩富文本格式 (RTF) 从**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中使用的压缩文件格式。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT WrapCompressedRTFStream(
  LPSTREAM lpCompressedRTFStream,
  ULONG ulflags,
  LPSTREAM FAR * lpUncompressedRTFStream
);
```

## <a name="parameters"></a>参数

 _lpCompressedRTFStream_
  
> [in]到上一条消息的 PR_RTF_COMPRESSED 属性打开流的指针。 
    
 _ulFlags_
  
> [in]函数标记选项的位掩码。 可以设置以下标志：
    
MAPI_MODIFY 
  
> 是否客户端打算读取或写入返回的换行的流接口。 
    
STORE_UNCOMPRESSED_RTF 
  
> 未压缩的 RTF 应写入所指的_lpCompressedRTFStream_流
    
 _lpUncompressedRTFStream_
  
> [输出]指向**WrapCompressedRTFStream**其中返回 stream 的未压缩 RTF 的位置的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

如果_ulFlags_参数中传递 MAPI_MODIFY 标志，则_lpCompressedRTFStream_参数必须已被打开的读取和写入。 新的、 未压缩 RTF 的文本应写入_lpUncompressedRTFStream_中返回的流接口。 因为它不可能要追加的现有流，必须编写的整个邮件文本。 
  
如果_ulFlags_参数中传递零，则然后_lpCompressedRTFStream_可能是以只读方式打开。 可以利用_lpUncompressedRTFStream_中返回的流接口读取只将整个邮件文本。 不能开始 stream 的中间搜索。 
  
 **WrapCompressedRTFStream**假定压缩的流的指针设置为 stream 的开头。 返回未压缩流不支持某些 OLE **IStream**方法。 包括**IStream::Clone**、 **IStream::LockRegion**、 **IStream::Revert**、 **IStream::Seek**、 **IStream::SetSize**、 **IStream::Stat**和**IStream::UnlockRegion**。 若要复制到整个流，需要读/写循环。 
  
客户端未压缩格式写入新 RTF，因为它应使用**WrapCompressedRTFStream**，而不是直接写入到流。 RTF 感知客户端应 STORE_UNCOMPRESSED_RTF 标志**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中搜索，并将其传递给**WrapCompressed RTFStream** ，如果将其设置。 
  
## <a name="see-also"></a>另请参阅



[RTFSync](rtfsync.md)

