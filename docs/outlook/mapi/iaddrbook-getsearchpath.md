---
title: IAddrBookGetSearchPath
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.GetSearchPath
api_type:
- COM
ms.assetid: 43b51a66-71fa-4e10-93e4-d533b48af4de
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f8c129e772870804ef464765b2035a3582317a09
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412980"
---
# <a name="iaddrbookgetsearchpath"></a>IAddrBook::GetSearchPath

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 方法启动的名称解析过程中要包含的容器的条目标识符的有序列表。 
  
```cpp
HRESULT GetSearchPath(
  ULONG ulFlags,
  LPSRowSet FAR * lppSearchPath
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制搜索路径中返回的字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _lppSearchPath_
  
> [out]指向指向容器条目标识符的有序列表的指针的指针。 **GetSearchPath** 将排序列表存储在 [SRowSet](srowset.md) 结构中。 如果通讯簿层次结构中没有任何容器，则 **SRowSet** 结构中返回零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索搜索路径。
    
## <a name="remarks"></a>备注

客户端和服务提供商调用 **GetSearchPath** 方法来获取用于用 **ResolveName** 方法解析名称的搜索路径。 通常，客户端调用 [IAddrBook：：SetSearchPath](iaddrbook-setsearchpath.md) 方法在配置文件中建立容器搜索路径，然后再调用 **GetSearchPath** 进行检索。 但是，调用 **SetSearchPath** 是可选的。 
  
如果从未调用过 **SetSearchPath，GetSearchPath** 会通过处理通讯簿的层次结构表来构建路径。  **GetSearchPath** 建立的默认搜索路径由以下容器组成，顺序如下： 
  
1. 具有读/写权限的第一个容器，通常为 PAB (个人) 。
    
2. 每个具有[PidTagDisplayType PR_DISPLAY_TYPE (PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 设置为 DT_GLOBAL。  此设置指示容器保留收件人。 
    
3. 如果 PR_DISPLAY_TYPE 属性中没有设置 **DT_GLOBAL** 标志的容器，且默认容器与具有读/写权限的第一个容器不同，则指定为默认值的容器。 
    
如果 **已调用 SetSearchPath，GetSearchPath** 会使用已存储在配置文件中的通讯簿容器构建路径。  **GetSearchPath** 先验证此路径，然后再将路径返回给调用方。 
  
首次调用 **SetSearchPath** 后，对 **SetSearchPath** 的后续调用必须用于修改 **GetSearchPath 返回的搜索路径**。 换句话说，调用客户端或提供商在首次调用 **SetSearchPath** 之后不会收到默认搜索路径。
  
## <a name="see-also"></a>另请参阅



[IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md)
  
[SRowSet](srowset.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

