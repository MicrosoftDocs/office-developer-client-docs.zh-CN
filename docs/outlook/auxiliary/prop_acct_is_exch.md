---
title: PROP_ACCT_IS_EXCH
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 599bfc7d-7b62-7cc1-69ff-6db04c96a49b
description: 如果该帐户是 Exchange 帐户，则为 true。
ms.openlocfilehash: db9f5ae46096d221ac3636a44f588c6a90ce146e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774422"
---
# <a name="propacctisexch"></a>PROP_ACCT_IS_EXCH

如果该帐户是 Exchange 帐户，则为 true。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0014  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|属性标记：  <br/> |0x00140003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。 如果客户端试图设置该属性，则此属性返回**E_OLK_PROP_READ_ONLY**。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

