---
title: ITnefOpenTaggedBody
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.OpenTaggedBody
api_type:
- COM
ms.assetid: 70d5b34c-85b3-4d1f-860e-2838947ba428
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 154d6e4a4e333f3a6165c3875bdcd57957ebf70c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348732"
---
# <a name="itnefopentaggedbody"></a>ITnef::OpenTaggedBody

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开封装的邮件的文本上的流接口。
  
```cpp
HRESULT OpenTaggedBody(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a>参数

 _lpMessage_
  
> 实时指向与流关联的邮件的指针。 此消息不需要与在对[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的调用中传递的邮件相同。 
    
 _ulFlags_
  
> 实时控制流接口打开方式的标志的位掩码。 可以设置以下标志:
    
MAPI_CREATE 
  
> 如果某一属性不存在于当前邮件中, 则应创建该属性。 如果该属性存在, 则应将属性中的当前数据替换为来自非特定于传输的封装格式 (TNEF) 流中的数据。 当某个实现设置 MAPI_CREATE 标志时, 它还应设置 MAPI_MODIFY 标志。
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认接口是只读的。 只要设置了 MAPI_CREATE, 就必须设置 MAPI_MODIFY。
    
 _lppStream_
  
> 排除指向 stream 对象的指针, 该对象包含已传递的封装邮件的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中的文本, 并支持[IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream)接口。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>注解

传输提供程序、邮件存储提供程序和网关调用**ITnef:: OpenTaggedBody**方法, 打开封装邮件的文本 (即 TNEF 对象) 上的流接口。 
  
在处理过程中, **OpenTaggedBody**会插入或分析附件标记, 以指示邮件文本中任何附件或 OLE 对象的位置。 附件标记采用以下格式: 
  
 **[[** 附件_名称_ **:** _附件容器名称_**中的** _n_ **]]**
  
 _附件名称_描述了附件对象; _n_是一个数字, 用于标识作为序列一部分的附件, 从[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的_lpKey_参数中传递的值增加;和_附件容器名称_描述了附件对象所在的物理组件。 
  
 **OpenTaggedBody**读取邮件文本, 并在附件对象最初显示在文本中的任何位置插入附件标记。 原始邮件文本不会更改。 
  
将带有标记的邮件传递给流时, 将去除这些标记, 并在流中标记的位置重新定位附件对象。
  
## <a name="see-also"></a>另请参阅



[OpenTnefStream](opentnefstream.md)
  
[OpenTnefStreamEx](opentnefstreamex.md)
  
[PidTagBody 规范属性](pidtagbody-canonical-property.md)
  
[ITnef : IUnknown](itnefiunknown.md)

