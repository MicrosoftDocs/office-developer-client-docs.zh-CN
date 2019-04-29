---
title: PROP_ACCT_MINI_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 30d8268e-0c64-401d-8799-e8e1ba78b88f
description: 返回一个帐户标识符, 该标识符在 Outlook 配置文件中是唯一的。
ms.openlocfilehash: 209f7dd89b8d947b999f2a068373aaf61a3e9784
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409431"
---
# <a name="propacctminiuid"></a>PROP_ACCT_MINI_UID

返回一个帐户标识符, 该标识符在 Outlook 配置文件中是唯一的。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0003  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|属性标记：  <br/> |0x00030003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。 如果客户端尝试设置此属性, 则此属性返回**E_OLK_PROP_READ_ONLY**。 
  
此属性与[PROP_ACCT_ID](prop_acct_id.md)的不同之处是, 它的值唯一标识在其中创建帐户的配置文件内和外部的帐户, 而**PROP_ACCT_ID**仅在一个配置文件中的所有帐户之间是唯一的帐户的创建时间。 当具有这些属性的邮件将漫游到具有不同 Outlook 配置文件的另一台计算机和不同的帐户集时, **PROP_ACCT_MINI_UID**可以唯一地标识原始配置文件中的原始帐户。 但是, **PROP_ACCT_ID**可能会与第二台计算机的配置文件中的帐户发生冲突。 
  
## <a name="see-also"></a>另请参阅

- [PROP_ACCT_ID](prop_acct_id.md)  
- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

