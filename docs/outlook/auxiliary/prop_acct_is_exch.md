---
title: PROP_ACCT_IS_EXCH
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 599bfc7d-7b62-7cc1-69ff-6db04c96a49b
description: 如果帐户是 Exchange 帐户, 则为 True。
ms.openlocfilehash: 2df750b208ff9d2a18cb0d7c22ec6b32b658c7b4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418230"
---
# <a name="propacctisexch"></a>PROP_ACCT_IS_EXCH

如果帐户是 Exchange 帐户, 则为 True。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0014  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|属性标记：  <br/> |0x00140003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。 如果客户端尝试设置此属性, 则此属性返回**E_OLK_PROP_READ_ONLY**。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

