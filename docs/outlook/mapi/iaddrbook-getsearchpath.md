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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341389"
---
# <a name="iaddrbookgetsearchpath"></a>IAddrBook::GetSearchPath

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回要包含在由[IAddrBook:: ResolveName](iaddrbook-resolvename.md)方法启动的名称解析进程中的容器的条目标识符的已排序列表。 
  
```cpp
HRESULT GetSearchPath(
  ULONG ulFlags,
  LPSRowSet FAR * lppSearchPath
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时标志的位掩码, 用于控制在搜索路径中返回的字符串的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _lppSearchPath_
  
> 排除指向指向容器条目标识符的有序列表的指针的指针。 **GetSearchPath**将排序列表存储在[SRowSet](srowset.md)结构中。 如果通讯簿层次结构中没有容器, 则在**SRowSet**结构中返回零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索搜索路径。
    
## <a name="remarks"></a>注解

客户端和服务提供程序调用**GetSearchPath**方法, 以获取用于使用**ResolveName**方法解析名称的搜索路径。 通常情况下, 客户端调用[IAddrBook:: SetSearchPath](iaddrbook-setsearchpath.md)方法在配置文件中建立容器搜索路径, 然后再调用**GetSearchPath**检索该路径。 但是, 调用**SetSearchPath**是可选的。 
  
如果从未调用过**SetSearchPath** , 则**GetSearchPath**通过通讯簿的层次结构表来生成路径。 由**GetSearchPath**建立的默认搜索路径由以下容器组成, 顺序如下: 
  
1. 第一个具有读/写权限的容器, 通常是个人通讯簿 (PAB)。
    
2. 将其**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 属性设置为 DT_GLOBAL 的每个容器。 此设置指示容器保留收件人。 
    
3. 如果没有在其**PR_DISPLAY_TYPE**属性中设置 DT_GLOBAL 标志且默认容器不同于具有读/写权限的第一个容器的容器, 则指定为默认容器。 
    
如果已调用**SetSearchPath** , 则**GetSearchPath**将使用存储在配置文件中的通讯簿容器生成路径。 **GetSearchPath**在将此路径返回给调用方之前对其进行验证。 
  
在首次调用**SetSearchPath**后, 必须使用对**SetSearchPath**的后续调用来修改**GetSearchPath**返回的搜索路径。 换言之, 在首次调用**SetSearchPath**之后, 调用客户端或提供程序不会收到默认搜索路径。
  
## <a name="see-also"></a>另请参阅



[IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md)
  
[SRowSet](srowset.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

