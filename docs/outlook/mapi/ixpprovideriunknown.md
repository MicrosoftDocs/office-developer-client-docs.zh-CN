---
title: IXPProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPProvider
api_type:
- COM
ms.assetid: d5507785-c924-4981-ae80-19709ceb054d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0aa77ced9d0c242dcafb84ca1e1a60d02db9504a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357447"
---
# <a name="ixpprovider--iunknown"></a>IXPProvider : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
初始化传输提供程序对象, 并在不再需要该对象时关闭该对象。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|公开者:  <br/> |传输提供程序对象  <br/> |
|实现者：  <br/> |传输提供程序  <br/> |
|调用者：  <br/> |MAPI 后台处理程序  <br/> |
|接口标识符:  <br/> |IID_IXPProvider  <br/> |
|指针类型:  <br/> |LPXPROVIDER  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[关闭](ixpprovider-shutdown.md) <br/> |以有序的方式关闭传输提供程序。  <br/> |
|[TransportLogon](ixpprovider-transportlogon.md) <br/> |建立一个会话, 客户端应用程序在该会话中登录到传输提供程序。  <br/> |
   

