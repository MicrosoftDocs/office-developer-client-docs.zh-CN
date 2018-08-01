---
title: PROP_ACCT_USER_EMAIL_ADDR
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fe447899-d37a-4775-a09d-13ba3a878008
description: 指定的帐户的电子邮件地址。
ms.openlocfilehash: 7d0bbba2dcb104326c360da6a10f3e19d1740e46
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774440"
---
# <a name="propacctuseremailaddr"></a>PROP_ACCT_USER_EMAIL_ADDR

指定的帐户的电子邮件地址。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x000C  <br/> |
|属性类型  <br/> |PT_UNICODE  <br/> |
|属性标记：  <br/> |0x000C001F  <br/> |
|访问权限  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>备注

 **PROP_ACCT_USER_EMAIL_ADDR**不应存在于每个帐户上。 例如，Exchange 帐户可以具有[PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md)但未为**PROP_ACCT_USER_EMAIL_ADDR**，而对于 SMTP/POP3 帐户，这种情况将被颠倒。
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)

