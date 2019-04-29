---
title: PROP_ACCT_USER_EMAIL_ADDR
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fe447899-d37a-4775-a09d-13ba3a878008
description: 指定帐户的电子邮件地址。
ms.openlocfilehash: 115941fdf2fdec01da8d6bc1320ac6cdc0930ffa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436774"
---
# <a name="propacctuseremailaddr"></a>PROP_ACCT_USER_EMAIL_ADDR

指定帐户的电子邮件地址。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x000C  <br/> |
|属性类型  <br/> |PT_UNICODE  <br/> |
|属性标记：  <br/> |0x000C001F  <br/> |
|访问权限  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>说明

 **PROP_ACCT_USER_EMAIL_ADDR**不应在每个帐户上都存在。 例如, Exchange 帐户可以具有[PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md) , 而不是**PROP_ACCT_USER_EMAIL_ADDR**, 而对于 SMTP/POP3 帐户, 则会还原该情况。
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)

