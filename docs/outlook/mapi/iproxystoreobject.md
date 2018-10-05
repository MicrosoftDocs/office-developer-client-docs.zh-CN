---
title: IProxyStoreObject
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProxyStoreObject
api_type:
- COM
ms.assetid: 567bede4-39a3-bfb4-af85-ba678e2cf4a5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 485d3f3cd4b6be4748a2ebf2ba0d0b71f691478f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395306"
---
# <a name="iproxystoreobject"></a>IProxyStoreObject

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供 Internet 消息访问协议 (IMAP) 存储对象的已解包并不调用同步和下载项目的情况下允许访问个人文件夹文件 (PST) 中的项。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) <br/> |
|供稿人：  <br/> |消息存储提供程序  <br/> |
|接口标识符：  <br/> |**IID_IProxyStoreObject** <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
|[IProxyStoreObject::UnwrapNoRef](iproxystoreobject-unwrapnoref.md) <br/> |获取一个指向解包 IMAP 存储区。  <br/> |
| *占位符成员*  <br/> | *不受支持或记录。*  <br/> |
   
## <a name="remarks"></a>说明

对要获取**IProxyStoreObject**接口的源消息存储调用[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 。 然后调用**IProxyStoreObject::UnwrapNoRef**获取解包的 store 对象。 如果**QueryInterface**返回错误**MAPI_E_INTERFACE_NOT_SUPPORTED**，然后存储不具有已包装。 
  
由于**UnwrapNoRef**不会增加到解包的存储对象，此新指针的引用计数成功调用**UnwrapNoRef**后，您应调用[IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)维护引用计数。 
  

