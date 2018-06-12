---
title: PROP_ACCT_MINI_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 30d8268e-0c64-401d-8799-e8e1ba78b88f
description: 返回 Outlook 配置文件之间都是唯一的帐户标识符。
ms.openlocfilehash: 9b2e30c0f57a54af219e68a8c2fe91e5dba4ddbe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774436"
---
# <a name="propacctminiuid"></a>PROP_ACCT_MINI_UID

返回 Outlook 配置文件之间都是唯一的帐户标识符。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0003  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|属性标记：  <br/> |0x00030003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>备注

通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。 如果客户端试图设置该属性，则此属性返回**E_OLK_PROP_READ_ONLY**。 
  
此属性是不同[PROP_ACCT_ID](prop_acct_id.md) ，其值唯一标识的帐户内部和外部的配置文件，在其中创建该帐户，而**PROP_ACCT_ID**是仅唯一的一个配置文件中的所有帐户在其中创建该帐户。 当包含这些属性的消息漫游拖放到不同的 Outlook 配置文件的帐户的不同组与另一台计算机上时， **PROP_ACCT_MINI_UID**可以唯一标识原始的配置文件中的原始帐户。 但是， **PROP_ACCT_ID**可以使用第二台计算机的配置文件中的帐户可能冲突。 
  
## <a name="see-also"></a>另请参阅

- [PROP_ACCT_ID](prop_acct_id.md)  
- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

