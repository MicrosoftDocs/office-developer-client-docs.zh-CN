---
title: GetTnefStreamCodepage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0f22ccf2-1004-4731-9d68-f66c01b4588b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1e3d384f35726ff28bb47f3d537c8a7a1dda6dce
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399653"
---
# <a name="gettnefstreamcodepage"></a>GetTnefStreamCodepage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定传输中性封装格式 (TNEF) 流的代码页。
  
|||
|:-----|:-----|
|标头文件：  <br/> |tnef.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商。  <br/> |
   
```cpp
HRESULT GetTnefStreamCodepage(
  LPSTREAM lpStream,
  ULONG FAR * lpulCodepage,
  ULONG FAR * lpulSubCodepage
);
```

## <a name="parameters"></a>参数

 _lpStream_
  
> [in]指向提供源 TNEF 流邮件存储 stream 对象 OLE **IStream**接口的指针。 
    
 _lpulCodepage_
  
> [输出]到流的代码页的指针。
    
 _lpulSubCodepage_
  
> [输出]到的流 subcode 页的指针。
    
## <a name="return-value"></a>返回值

 **S_OK**
  
> 呼叫成功或多个预期值返回。
    
 **MAPI_E_NOT_ENOUGH_DISK**
  
> 读取流中的 TNEF 属性时出错。
    
 **MAPI_E_CORRUPT_DATA**
  
> 流未 TNEF 流，或时出错读取 attOemCodepage 属性。
    
## <a name="remarks"></a>说明

使用**GetTnefStreamCodepage**函数读取 TNEF 流来确定的代码页和子代码页的**attOemCodepage**属性。 如果找不到**attOemCodepage** ， **GetTnefStreamCodepage**返回 437 代码页和 subcode 页为 0。 
  
## <a name="see-also"></a>另请参阅



[attOemCodepage](https://msdn.microsoft.com/library/ee158667%28EXCHG.80%29.aspx)

