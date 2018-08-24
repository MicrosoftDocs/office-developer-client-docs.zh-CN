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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7bf69e560142ab282d6545389e02766389e4d018
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580696"
---
# <a name="iaddrbookgetsearchpath"></a>IAddrBook::GetSearchPath

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个已排序的列表项标识符启动[IAddrBook::ResolveName](iaddrbook-resolvename.md)方法的名称解析进程中包含的容器。 
  
```cpp
HRESULT GetSearchPath(
  ULONG ulFlags,
  LPSRowSet FAR * lppSearchPath
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]中的搜索路径返回控制的字符串类型的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _lppSearchPath_
  
> [输出]指向一个已排序列表容器项标识符的指针的指针。 **GetSearchPath** [SRowSet](srowset.md)结构中存储的有序列的表。 如果通讯簿层次结构中不有任何容器， **SRowSet**结构中将返回零。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索的搜索路径。
    
## <a name="remarks"></a>注解

客户端和服务提供商调用**GetSearchPath**方法以获取用于将名称解析使用**ResolveName**方法的搜索路径。 通常情况下，客户端调用[IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md)方法之前呼叫**GetSearchPath**检索该配置文件中建立容器搜索路径。 但是，调用**SetSearchPath**是可选的。 
  
如果**SetSearchPath**调用过， **GetSearchPath**生成一个路径由通过地址的工作簿的层次结构表。 默认的搜索路径建立**GetSearchPath**包括以下容器按以下顺序： 
  
1. 第一个容器具有读/写权限，通常在个人通讯簿 (PAB)。
    
2. 其**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 属性设置为 DT_GLOBAL 每个容器。 此设置表示该容器包含收件人。 
    
3. 容器被指定为默认值，如果有其**PR_DISPLAY_TYPE**属性和默认容器中设置 DT_GLOBAL 标志没有容器与第一个容器具有读/写权限。 
    
如果已调用**SetSearchPath** ， **GetSearchPath**使用已存储在配置文件中的地址簿容器生成一个路径。 **GetSearchPath**返回给调用方之前验证此路径。 
  
后**SetSearchPath**到第一个呼叫，必须使用后的面对**SetSearchPath**修改**GetSearchPath**返回的搜索路径。 换句话说，该呼叫的客户端或提供程序不会收到默认的搜索路径后**SetSearchPath**到第一个呼叫。
  
## <a name="see-also"></a>另请参阅



[IAddrBook::SetSearchPath](iaddrbook-setsearchpath.md)
  
[SRowSet](srowset.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

