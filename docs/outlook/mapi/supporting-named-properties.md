---
title: 支持命名属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2e742ecd-2dcd-46a8-9d4e-2cec2c6f795e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 27625e913f06e858295351ed62de840ae7789915
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349628"
---
# <a name="supporting-named-properties"></a>支持命名属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
实现 [IMAPIProp: IUnknown](imapipropiunknown.md) 界面的任何对象可支持命名属性。 对命名属性的支持是必需的: 
  
- 允许将其他提供程序中的条目复制到其容器中的通讯簿提供程序。
    
- 可用于创建任意邮件类型的邮件存储提供程序。
    
命名属性支持对于所有其他服务提供程序都是可选的。 支持命名属性的服务提供程序必须在[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法中实现名称到标识符的映射。 客户端调用**GetNamesFromIDs**以检索 over 0x8000 范围和**GetIDsFromNames**中的一个或多个属性标识符对应的名称, 以创建或检索一个或多个名称的标识符。 
  
不支持命名属性的服务提供程序必须:
  
- 通过在[SPropProblem](spropproblem.md)数组中返回 MAPI_E_UNEXPECTED_ID, 对[IMAPIProp:: SetProps](imapiprop-setprops.md)的调用失败, 以设置具有0x8000 或更高的标识符的属性。 
    
- 从[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)和[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法返回 MAPI_E_NO_SUPPORT。 
    

