---
title: 支持命名的属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2e742ecd-2dcd-46a8-9d4e-2cec2c6f795e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9ee41469914e52295af219428f26854662c9e2f9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582244"
---
# <a name="supporting-named-properties"></a>支持命名的属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
实现任何对象[IMAPIProp: IUnknown](imapipropiunknown.md)接口可支持命名的属性。 支持的命名属性是必需的： 
  
- 通讯簿提供程序，以允许从其他提供程序复制到其容器的条目。
    
- 消息存储提供程序可用于创建任意消息类型。
    
对于所有其他服务提供程序是可选的命名的属性支持。 服务提供商支持的命名属性必须实现的[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法中的名称为标识符映射。 客户端呼叫**GetNamesFromIDs**检索转移 0x8000 范围中的一个或多个属性标识符的相应名称和**GetIDsFromNames**创建或检索一个或多个名称的标识符。 
  
服务提供程序不支持的命名属性必须：
  
- 无法对[IMAPIProp::SetProps](imapiprop-setprops.md)调用，以通过[SPropProblem](spropproblem.md)数组中返回 MAPI_E_UNEXPECTED_ID 设置与标识符的 0x8000 或更高版本的属性。 
    
- 从[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法的调用返回 MAPI_E_NO_SUPPORT。 
    

