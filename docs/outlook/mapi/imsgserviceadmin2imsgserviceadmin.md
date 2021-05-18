---
title: IMsgServiceAdmin2 IMsgServiceAdmin
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin2
api_type:
- COM
ms.assetid: 14654259-e884-46bf-84ff-9e3c1a8cd60d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2b1e00938800fb6517e634c3ba365276e0e76bd9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406869"
---
# <a name="imsgserviceadmin2--imsgserviceadmin"></a>IMsgServiceAdmin2 : IMsgServiceAdmin

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对配置文件中的邮件服务进行更改。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiaux.h  <br/> |
|公开者：  <br/> |邮件服务管理对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMsgServiceAdmin2  <br/> |
|指针类型：  <br/> |LPSERVICEADMIN2  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md) <br/> |将邮件服务添加到当前配置文件，并返回新添加的服务 UID。  <br/> |
   
## <a name="remarks"></a>备注

**IMsgServiceAdmin2** 接口由公开 [IMsgServiceAdmin](imsgserviceadminiunknown.md)接口的相同对象公开，自 Microsoft Outlook 2003 以来，已使用 Outlook 的 MAPI 子系统实现。 
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

