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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299431"
---
# <a name="gettnefstreamcodepage"></a>GetTnefStreamCodepage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定传输中性封装格式 (TNEF) 流的代码页。
  
|||
|:-----|:-----|
|标头文件：  <br/> |tnef  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序。  <br/> |
   
```cpp
HRESULT GetTnefStreamCodepage(
  LPSTREAM lpStream,
  ULONG FAR * lpulCodepage,
  ULONG FAR * lpulSubCodepage
);
```

## <a name="parameters"></a>参数

 _lpStream_
  
> 实时指向存储流对象 OLE **IStream**接口的指针, 该接口提供 TNEF 流消息的源。 
    
 _lpulCodepage_
  
> 排除指向流的代码页的指针。
    
 _lpulSubCodepage_
  
> 排除指向流的子代码页的指针。
    
## <a name="return-value"></a>返回值

 **S_OK**
  
> 调用成功, 并返回了所需的值或值。
    
 **MAPI_E_NOT_ENOUGH_DISK**
  
> 读取 TNEF 流中的属性时出错。
    
 **MAPI_E_CORRUPT_DATA**
  
> 流不是 TNEF 流, 或者读取 attOemCodepage 属性时出错。
    
## <a name="remarks"></a>注解

使用**GetTnefStreamCodepage**函数可读取 TNEF 流的**attOemCodepage**属性, 以确定 "代码页" 和 "子代码" 页。 如果找不到**attOemCodepage** , 则**GetTnefStreamCodepage**将返回437和子代码页面0的代码页。 
  
## <a name="see-also"></a>另请参阅



[attOemCodepage](https://msdn.microsoft.com/library/ee158667%28EXCHG.80%29.aspx)

