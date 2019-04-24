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
  
提供已解开的 Internet 邮件访问协议 (IMAP) 存储对象, 并允许访问个人文件夹文件 (PST) 中的项目, 而无需调用同步并下载这些项目。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自:  <br/> |[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) <br/> |
|提供者:  <br/> |邮件存储区提供程序  <br/> |
|接口标识符:  <br/> |**IID_IProxyStoreObject** <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
|[IProxyStoreObject::UnwrapNoRef](iproxystoreobject-unwrapnoref.md) <br/> |获取一个指向未解包的 IMAP 存储区的指针。  <br/> |
| *占位符成员*  <br/> | *不支持或记录。*  <br/> |
   
## <a name="remarks"></a>注解

调用[IUnknown::](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)源邮件存储上的 QueryInterface, 以获取**IProxyStoreObject**接口。 然后, 调用**IProxyStoreObject:: UnwrapNoRef**获取未包装的 store 对象。 如果**QueryInterface**返回错误**MAPI_E_INTERFACE_NOT_SUPPORTED**, 则存储尚未被包装。 
  
由于**UnwrapNoRef**不会将此新指针的引用计数增加到已解包的 store 对象, 因此在成功调用**UnwrapNoRef**后, 应调用[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)来维护引用计数。 
  

