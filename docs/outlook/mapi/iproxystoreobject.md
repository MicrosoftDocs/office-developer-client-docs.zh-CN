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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315517"
---
# <a name="iproxystoreobject"></a>IProxyStoreObject

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供一个 Internet 邮件访问协议 (IMAP) 存储对象，该对象已被取消包装，允许访问个人文件夹文件 (PST) 中的项目，而无需调用同步和下载项目。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自：  <br/> |[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) <br/> |
|提供方：  <br/> |邮件存储提供程序  <br/> |
|接口标识符：  <br/> |**IID_IProxyStoreObject** <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
|[IProxyStoreObject::UnwrapNoRef](iproxystoreobject-unwrapnoref.md) <br/> |获取一个指向未包装的 IMAP 存储的指针。  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
   
## <a name="remarks"></a>备注

对 [源邮件存储调用 IUnknown：：QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 以获取 **IProxyStoreObject** 接口。 然后调用 **IProxyStoreObject：：UnwrapNoRef** 以获取未包装存储对象。 如果 **QueryInterface** 返回错误 **MAPI_E_INTERFACE_NOT_SUPPORTED，** 则存储尚未封装。 
  
由于 **UnwrapNoRef** 不增加指向未包装存储对象的此新指针的引用计数，因此在成功调用 **UnwrapNoRef** 后，应调用 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) 以保持引用计数。 
  

